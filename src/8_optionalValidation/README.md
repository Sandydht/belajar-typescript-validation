# Optional Validation
* Secara default, saat membuat schema, data akan selalu wajib diisi.
* Namun kadang kita butuh data yang tidak wajib, atau optional.
* Kita bisa menggunakan ``` optional() ``` method pada schema, untuk menjadikan bahwa field tersebut tidak wajib.
* Kode: Optional Validation
  ```TSX
  it('should can support optional validation', async () => {
    const registerSchema = z.object({
      username: z.string().email(),
      password: z.string().min(6).max(20),
      firstName: z.string().min(3).max(100),
      lastName: z.string().min(3).max(100).optional()
    });

    const request = {
      username: 'sandy@email.com',
      password: '123456',
      firstName: 'Sandy'
    };

    const result = registerSchema.parse(request);
    console.log(result);
  });
  ```
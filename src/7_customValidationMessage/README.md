# Custom Validation Message
* Saat kita menggunakan zod, secara default sudah terdapat message error.
* Namun, jika kita ingin ubah message errornya, kita bisa ubah ketika menggunakan method di schema.
* Kode: Custom Validation Message
  ```TSX
  it('should can validate object with message', () => {
    const loginSchema = z.object({
      username: z.string().email('username harus email'),
      password: z.string().min(6, 'password min harus 6 karakter').max(20, 'password max harus 20 karakter')
    });

    const request = {
      username: 'Sandy',
      password: '123'
    };

    try {
      loginSchema.parse(request);
    } catch (err) {
      if (err instanceof ZodError) {
        console.info(err.errors);
        err.errors.forEach((e) => {
          console.info(e.message);
        });
      }
    }
  });
  ```
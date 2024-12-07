# Object Validation
* Saat kita membuat aplikasi, kita sering sekali membuat JavaScript object.
* Untungnya zod juga bisa digunakan untuk melakukan validasi JS Object, sehingga mempermudah kita untuk melakukan sekaligus ke semua field di JS Object.
* [https://zod.dev/?id=objects](https://zod.dev/?id=objects)
* Kode: Object Validation
  ```TSX
  it('should can validate object', () => {
    const loginSchema = z.object({
      username: z.string().email(),
      password: z.string().min(6).max(20)
    });

    const request = {
      username: 'sandy@test.com',
      password: '12345678',
      ignore: 'ignore'
    };

    const result = loginSchema.parse(request);
    console.info(result);
  });
  ```

# Nested Object
* Zod juga bisa digunakan untuk memvalidasi nested object.
* Saat kita ingin memvalidasi nested object, kita harus tentukan object schema nya juga.
* Kode: Nested Object
  ```TSX
  it('should can validated nested object', () => {
    const createUserSchema = z.object({
      id: z.string().max(100),
      name: z.string().max(100),
      address: z.object({
        street: z.string().max(100),
        city: z.string().max(100),
        zip: z.string().max(10),
        country: z.string().max(100)
      })
    });

    const request = {
      id: '123',
      name: 'Sandy',
      address: {
        street: 'Jl. Surya K',
        city: 'Jakarta',
        zip: '12345',
        country: 'Indonesia'
      }
    };

    const result = createUserSchema.parse(request);
    console.info(result);
  });
  ```
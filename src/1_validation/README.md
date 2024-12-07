# Validation
* Zod mendukung validasi untuk banyak tipe data TypeScript, seperti string, number, boolean, dan lain - lain.
* Untuk menggunakan Zod, kita cukup import z dari package zod.
* Selanjutnya, kita bisa menggunakan method - method sesuai dengan tipe datanya.

# Schema
* Hal pertama yang perlu kita lakukan untuk melakukan validasi adalah membuat schema.
* Schema adalah aturan - aturan yang sudah kita tentukan.
* Setelah membuat schema, baru selanjutnya kita bisa melakukan validasi data menggunakan schema tersebut.
* Kode: Membuat Schema
  ```TSX
  import { z } from 'zod';

  describe('zod', () => {
    it('should support validation', () => {
      const schema = z.string().min(3).max(100)

      const request = 'Sandy';

      const result = schema.parse(request);
      expect(result).toBe(request);
    });
  });
  ```

# Validasi Tipe Data
* String: [https://zod.dev/?id=strings](https://zod.dev/?id=strings)
* Number: [https://zod.dev/?id=numbers](https://zod.dev/?id=numbers)
* Boolean: [https://zod.dev/?id=booleans](https://zod.dev/?id=booleans)
* Kode: Validasi
  ```TSX
  it('should support validate primitive data type', () => {
    const usernameSchema = z.string().email();
    const isAdminSchema = z.boolean();
    const priceSchema = z.number().min(1000).max(10000000);

    const username = usernameSchema.parse('sandy@email.com');
    console.info(username);

    const isAdmin = isAdminSchema.parse(true);
    console.info(isAdmin);

    const price = priceSchema.parse(1000000);
    console.info(price);
  });
  ```
# Konversi Tipe Data
* Saat kita membuat schema untuk tipe data seperti string, number, dan boolean, kita harus melakukan ``` parse() ``` menggunakan tipe yang sama.
* Kadang - kadang, input dari pengguna bisa menggunakan tipe data berbeda, contoh input number berupa string "1234", input boolean berupa string "true".
* Zod memiliki object bernama ``` coerce ``` yang bisa digunakan untuk melakukan konversi tipe data secara otomatis.
* Kode: Konversi Tipe Data
  ```TSX
  it('should support data conversion', () => {
    const usernameSchema = z.coerce.string().min(3).max(20);
    const isAdminSchema = z.coerce.boolean();
    const priceSchema = z.coerce.number().min(1000).max(10000000);

    const username = usernameSchema.parse(12345);
    console.info(username);

    const isAdmin = isAdminSchema.parse("true");
    console.info(isAdmin);

    const price = priceSchema.parse("1000000");
    console.info(price);
  });
  ```
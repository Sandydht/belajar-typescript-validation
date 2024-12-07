# Date Validation
* Zod juga bisa digunakan untuk melakukan validasi tipe data Date.
* [https://zod.dev/?id=dates](https://zod.dev/?id=dates)
* Kode: Date Validation
  ```TSX
  it('should support date validation', () => {
    const birthDateSchema = z.coerce.date().min(new Date(1980, 0, 1)).max(new Date(2020, 0, 1));

    const birtDate = birthDateSchema.parse("1990-01-01");
    console.info(birtDate);

    const birtDate2 = birthDateSchema.parse(new Date(1990, 10, 10));
    console.info(birtDate2);
  });
  ```
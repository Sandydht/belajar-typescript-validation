# Custom Validation
* Saat menggunakan ``` transform() ```, kita bisa menambahkan parameter kedua yaitu ``` RefinementCtx ```, dimana bisa kita gunakan untuk menambah issue jika terjadi masalah.
* Hal ini bisa digunakan sebagai custom validation.
* Kode: RefinementCtx
  ```TSX
  export declare type RefinementCtx = {
    addIssue: (arg: IssueData) => void;
    path: (string | number)[];
  };
  ```
* Kode: Custom Validation
  ```TSX
  it('should an create custom validation', () => {
    const loginSchema = z.object({
      username: z.string().email().transform((data, ctx) => {
        if (data != data.toUpperCase()) {
          ctx.addIssue({
            code: z.ZodIssueCode.custom,
            message: 'username harus uppercase'
          });

          return z.NEVER;
        } else {
          return data;
        }
      }),
      password: z.string().min(6).max(20)
    });
  });
  ```
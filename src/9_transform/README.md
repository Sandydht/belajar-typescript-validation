# Transform
* Saat membuat schema, terdapat function bernama transform yang bisa kita gunakan untuk melakukan transformasi data setelah proses parse selesai.
* Kode: Transform
  ```TSX
  it('should can support transform', async () => {
    const schema = z.string().transform((data) => {
      return data.toUpperCase();
    });

    const result = schema.parse('sandy');
    console.log(result);
  });
  ```
# Collection Validation
* Selain object, kita juga bisa melakukan validasi untuk tipe data collection, seperti Array, Set, dan Map.
* [https://zod.dev/?id=arrays](https://zod.dev/?id=arrays)
* [https://zod.dev/?id=sets](https://zod.dev/?id=sets)
* [https://zod.dev/?id=maps](https://zod.dev/?id=maps)
* Kode: Array Validation
  ```TSX
  it('should can validate array', () => {
    const schema = z.array(z.string()).min(1).max(10);

    const request: Array<string> = ["a", "b", "c"];
    const result: Array<string> = schema.parse(request);

    console.log(result);
  });
  ```
* Kode: Set Validation
  ```TSX
  it('should can validate set', async () => {
    const schema = z.set(z.string()).min(1).max(10);

    const request: Set<string> = new Set(["a", "b", "c", "a", "b", "c"]);
    const result = schema.parse(request);

    console.log(result);
  });
  ```
* Kode: Map Validation
  ```TSX
  it('should can validate map', () => {
    const schema = z.map(z.string(), z.string());

    const request: Map<string, string> = new Map([
      ["name", "Sandy"],
      ["age", "28"]
    ]);
    const result = schema.parse(request);

    console.log(result);
  });
  ```
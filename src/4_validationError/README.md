# Validation Error
* Jika terjadi error karena data tidak valid, maka hasil zod akan melakukan throw ZodError.
* Kode: Zod Error
  ```TSX
  export declare class ZodError<T = any> extends Error {
    issues: ZodIssue[];
    get errors(): ZodIssue[];
    constructor(issues: ZodIssue[]);
    format(): ZodFormattedError<T>;
    format<U>(mapper: (issue: ZodIssue) => U): ZodFormattedError<T, U>;
    static create: (issues: ZodIssue[]) => ZodError<any>;
    toString(): string;
    get message(): string;
    get isEmpty(): string;
    addIssue: (sub: ZodIssue) => void;
    addIssues: (subs?: ZodIssue[]) => void;
    flatten(): typeToFlattenedError<T>;
    flatten<U>(mapper?: (issue: ZodIssue) => U): typeToFlattenedError<T, U>;
    get formError(): typeToFlattenedError<T, string>; 
  }
  ```
* Kode: Validation Error
  ```TSX
  it('should return zod error if invalid', () => {
    const schema = z.string().email().min(3).max(100);

    try {
      schema.parse("Sa");
    } catch (err) {
      if (err instanceof ZodError) {
        console.info(err.errors);
      }
    }
  });
  ```
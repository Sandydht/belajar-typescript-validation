# TypeScript Validation

## Pengenalan Validation
* Saat kita membuat aplikasi, validasi adalah salah satu hal yang sangat penting untuk kita lakukan.
* Validasi memastikan bahwa data sudah dalam keadaan benar atau sesuai sebelum di proses.
* Validasi dilakukan untuk menjaga agar kita tetap konsisten dan tidak rusak.
* Validasi biasanya dilakukan di kode aplikasi, dan di constraint table di database.

## Validasi TypeScript
* TypeScript sayangnya tidak menyediakan library untuk validasi, oleh karena itu kita perlu melakukan validasi secara manual.
* Tapi untungnya, banyak library yang dibuat oleh komunitas programmer TypeScript yang bisa kita gunakan untuk mempermudah kita melakukan validasi.
* Salah satu library yang populer untuk melakukan validasi adalah library Zod.
* [https://zod.dev/](https://zod.dev/)

## Membuat Project
* Buat folder belajar-typescript-validation
* ``` npm init ```
* Buka package.json, dan tambah ``` "type": "module" ```

## Menambah Library Jest untuk Unit Test
* ``` npm install --save-dev jest @types/jest ```
* [https://www.npmjs.com/package/jest](https://www.npmjs.com/package/jest)

## Menambah Library Babel
* ``` npm install --save-dev babel-jest @babel/preset-env ```
* [https://babeljs.io/setup#installation](https://babeljs.io/setup#installation)

## Menambah TypeScript
* ``` npm install --save-dev typescript ```
* [https://www.npmjs.com/package/typescript](https://www.npmjs.com/package/typescript)

## Setup Project TypeScript
* ``` npx tsc --init ```
* Semua konfigurasi akan dibuat di file tsconfig.json.
* Ubah ``` "module" ``` dari ``` "commonjs" ``` menjadi ``` "ES6" ```
* Ubah ``` "moduleResolution" ``` menjadi ``` "node" ```

## Setup TypeScript untuk Jest
* ``` npm install --save-dev @babel/preset-typescript ```
* ``` npm install --save-dev @jest/globals ```
* [https://jestjs.io/docs/getting-started#using-typescript](https://jestjs.io/docs/getting-started#using-typescript)

## Menginstall Zod
* ``` npm install zod ```

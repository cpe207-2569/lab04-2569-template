# Lab 04 : JavaScript/TypeScript #1

### ป้อนข้อมูลนักศึกษา

รหัส นศ.:

ชื่อ-สกุล :

ให้ นศ.เขียนโปรแกรมโดยใช้ Node.js + TypeScript ตามคำสั่งของโจทย์ในข้อต่าง ๆ ตามรายละเอียดด้านล่างนี้

[คลิกเพื่อดูรายละเอียด](https://o365cmu-my.sharepoint.com/:b:/g/personal/dome_potikanond_cmu_ac_th/EdeLE2HCcmdGrvFsxrhkd4YBaUrcORwG5WRAVMPJgksl8A?e=GCS5AV)

---

### คำอธิบายเกี่ยวกับการใช้งาน TypeScript

หากในโปรเจคโฟลเดอร์ยังไม่มี `package.json` ให้ initialize project ด้วยการ**รันคำสั่งต่อไปนี้ภายในโปรเจคโฟลเดอร์**

```bash
$ pnpm init
```

ติดตั้ง package ต่อไปนี้ ด้วยคำสั่งด้านล่าง

- `TypeScript` : เพื่อให้สามารถเขียนโค้ด TypeScript ในโปรเจคนี้
- `@types@node` : เพื่อเพิ่มข้อมูล Type definition ให้ node.js
- `tsx` เพื่อให้สามารถรันโค้ด TypeScript ได้โดยไม่ต้อง compile
- `nodemon` เพื่อให้สามารถรันโค้ด JavaScript ได้เมื่อไฟล์มีการเปลี่ยนแปลง (optional)

```bash
$ pnpm install -D typescript  @types/node  tsx nodemon
```

สร้างไฟล์ `tsconfig.json` เพื่อกำหนดค่าการทำงานให้ **TypeScript** ของโปรเจคนี้ โดยการรันคำสั่งต่อไปนี้ภายในโฟลเดอร์ของโปรเจค

```bash
$ pnpm exec tsc --init
```

แก้ไขค่าในไฟล์ `tsconfig.json` ในส่วนของ **`compilerOptions`** ดังต่อไปนี้

```json
"module": "commonjs",      // just for lab autograding
"target": "es2016",        // output script version
"types": ["node"],
"removeComments": false,   // remove comments
"noEmitOnError": true      // don't emit if there is an error

// Other Outputs           // comment these lines
// "sourceMap": true,
// "declaration": true,
// "declarationMap": true,
```

เมื่อต้องการรันไฟล์ TypeScript โดยไม่จำเป็นต้อง Compile สามารถใช้คำสั่งต่อไปนี้

```bash
$ node <filename.ts>
```

ทดลองทำการแปลงโค้ด TypeScript เป็น JavaScript ด้วยคำสั่งต่อไปนี้

```bash
// ในกรณีที่ติดตั้ง typescript ด้วยคำสั่ง 'npm install -D typescript'
$ pnpm exec tsc [filename.ts]

// ทำการ compile โค้ด TypeScript ทุกไฟล์
$ pnpm exec tsc
```

แล้วทำการรันไฟล์ JavaScript ด้วยคำสั่ง

```bash
$ node <filename.js>
```

หรือใช้ nodemon ในการรันไฟล์ JavaScript

```bash
$ pnpm exec nodemon <filename.js>
```

หรือใช้ nodemon ในการรันไฟล์ TypeScript

```bash
$ pnpm exec nodemon --exec tsx <filename.ts>
```

### ทดสอบการทำงานกับ Testcase ที่ใช้ในระบบ Classroom autograder

ระบบจะตรวจสอบการทำงานจากไฟล์ JavaScript ที่ได้จากการ compile เท่านั้น ดังนั้นจึงต้องทำการ compile ด้วยคำสั่ง `npx tsc <filename.ts>` เสียก่อน
จากนั้นตรวจการทำงานกับ Testcase ด้วยคำสั่ว

```bash
$ pnpm run test q1     // เพื่อตรวจข้อ q1
$ pnpm run test        // เพื่อตรวจทุกข้อ
```

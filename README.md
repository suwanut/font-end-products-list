# Font-end-products-list
Assignment Tests  จัดทำเว็บไซต์แสดงสินค้าโดยใช้ Nuxt js + Bootstrap  ส่วนงาน FRONT-END
เป็นส่วนหน้าเว็บไซต์ข้อมูลสินค้า จำนวน 25 รายการ และสามารถเข้าดูรายละเอียดได้แต่ละตัวสินค้า ประกอบด้วยข้อมูลดังนี้
- SKU สินค้า
- ชื่อสินค้า
- รูปภาพสินค้า
- ราคาสินค้า
- รายละเอียดสินค้า
- ขนาดสินค้า
- น้ำหนักสินค้า
(demo data)
## Requirements
-   Node v18.15.0
-   Git

## คำแนะนำ
 - สร้าง โฟล์เดอร์โปรเจ็ค 
 > `mkdir prd_list`
- Clone the repo and install the dependencies.
> `git clone https://github.com/suwanut/font-end-products-list.git`
- เข้าโปรเจ็ค 
> `cd prd_list`
 - ลง dependencies ต่างๆ  
> `npm install`

โปรเจ็คนี้ใช้ (package.json)
  >  `{
  "name": "prd_list",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "nuxt",
    "build": "nuxt build",
    "start": "nuxt start",
    "generate": "nuxt generate",
    "lint:js": "eslint --ext \".js,.vue\" --ignore-path .gitignore .",
    "lint:prettier": "prettier --check .",
    "lint": "npm run lint:js && npm run lint:prettier",
    "lintfix": "prettier --write --list-different . && npm run lint:js -- --fix"
  },
  "dependencies": {
    "@nuxt/content": "^1.0.0",
    "@nuxtjs/axios": "^5.13.6",
    "bootstrap": "^4.6.2",
    "bootstrap-vue": "^2.22.0",
    "core-js": "^3.25.3",
    "nuxt": "^2.15.8",
    "vue": "^2.7.10",
    "vue-server-renderer": "^2.7.10",
    "vue-template-compiler": "^2.7.10"
  },
  "devDependencies": {
    "@babel/eslint-parser": "^7.19.1",
    "@nuxtjs/eslint-config": "^11.0.0",
    "@nuxtjs/eslint-module": "^3.1.0",
    "eslint": "^8.24.0",
    "eslint-config-prettier": "^8.5.0",
    "eslint-plugin-nuxt": "^4.0.0",
    "eslint-plugin-vue": "^9.5.1",
    "prettier": "^2.7.1"
  }
}`

- Run project
> `npm run dev`
[PORT:3000]
Open  [http://localhost:3000](http://localhost:3000/) 

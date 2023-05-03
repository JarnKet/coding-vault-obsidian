> ເປັນການນຳໃຊ້ Tailwind ຮ່ວມກັບ Vite.js

## 1. ການຕິດຕັ້ງ
```shell
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

## 2. ການ Config
### 2.1 tailwind.config.js

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
 
    // Or if using `src` directory:
    "./src/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 2.2 global.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

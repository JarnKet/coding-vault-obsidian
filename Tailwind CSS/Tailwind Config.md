> ແນວທາງການຕັ້ງຄ່າຟາຍ ເພື່ອກຳນົດຄຸນລັກສະນະຂອງ Tailwind ເພື່ອສ້າງ Style ເປັນຂອງຕົນເອງ.

Source : https://tailwindcss.com/docs/configuration

```js
/** @type {import('tailwindcss').Config} */

module.exports = {
  content: [
    './src/pages/**/*.{js,ts,jsx,tsx}',
    './src/components/**/*.{js,ts,jsx,tsx}',
    './src/sections/**/*.{js,ts,jsx,tsx}',
  ],
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
	    //Example Color Code
        primary: '#00040f',
        secondary: '#00f6ff',
        dimWhite: 'rgba(255, 255, 255, 0.7)',
        dimBlue: 'rgba(9, 151, 124, 0.01)',
      },
    },
    fontFamily: {
	  //Example Font Family
      sourceCode: ['Source Code Pro', 'monospace'],
      notoLaos: ['Noto Sans Lao', 'sans-serif'],
    },
    screens: {
	  //Example Screen Ratio
      xs: '480px',
      ss: '620px',
      sm: '768px',
      md: '1060px',
      lg: '1200px',
      xl: '1700px',
    },
  },
  plugins: [],
};
```
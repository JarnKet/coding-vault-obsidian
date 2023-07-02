---
tag: npm-package, Next.js
---
> ເປັນ Package ທີ່ຊ່ວຍຈັດການເລື່ອງ Font ເພື່ອເພີ່ມປະສິດທິພາບຂອງເວັບໄຊທ໌ ແບບ SSG

Source: https://www.npmjs.com/package/@next/font

## 1. ການຕິດຕັ້ງ

``` shell
npm i @next/font
```

## 2. ການນຳໃຊ້

### 2.1 Google Fonts
```js
// pages/_app.js

// ນຳເອົາຊື່ Font ທີ່ຕ້ອງການເຂົ້າມາ
import { Roboto } from 'next/font/google'


// ສາມາດກຳນົດ Style ໃຫ້ກັບ Font ໄດ້
const roboto = Roboto({
  weight: ['400', '700'],
  style: ['normal', 'italic'],
  subsets: ['latin'],
})


// ນຳເອົາໄປກຳນົດໃຫ້ກັບ Component ດ້ວຍ fontName.className
export default function MyApp({ Component, pageProps }) {
  return (
    <main className={roboto.className}>
      <Component {...pageProps} />
    </main>
  )
}
```

#### 2.1.1 ການກຳນົດພາຍໃນ Tag `<head/>`
```js
// pages/_app.js
import { Inter } from 'next/font/google'

const inter = Inter({ subsets: ['latin'] })

// ກຳນົດ font-family ພາຍໃນແທັກ <style jsx global></style>
export default function MyApp({ Component, pageProps }) {
  return (
    <>
      <style jsx global>{`
        html {
          font-family: ${inter.style.fontFamily};
        }
      `}</style>
      <Component {...pageProps} />
    </>
  )
}
```

#### 2.1.2 ໃຊ້ສະເພາະໜ້າໃດໜຶ່ງເທົ່ານັ້ນ
```js
// pages/index.js
import { Inter } from 'next/font/google'

const inter = Inter({ subsets: ['latin'] })

export default function Home() {
  return (
    <div className={inter.className}>
      <p>Hello World</p>
    </div>
  )
}
```

### 2.2 Local Fonts
```js
// pages/_app.js

// import localFont ເຂົ້າມາໃຊ້
import localFont from 'next/font/local'

// Font files can be colocated inside of `pages`
// ສ້າງຕົວປ່ຽນເພື່ອເກັບ Font (ໃນສ່ວນຂອງ path ເຮົາຄວນໃສ່ຕາມຕຳແໜ່ງຕົວຈິງ)
const myFont = localFont({ src: './my-font.woff2' })

export default function MyApp({ Component, pageProps }) {
  return (
    <main className={myFont.className}>
      <Component {...pageProps} />
    </main>
  )
}
```

ນອກນັ້ນ, ຍັງສາມາດກຳນົດ style ໃຫ້ກັບ font ໄດ້ດ້ວຍ
```js
const roboto = localFont({
  src: [
    {
      path: './Roboto-Regular.woff2',
      weight: '400',
      style: 'normal',
    },
    {
      path: './Roboto-Italic.woff2',
      weight: '400',
      style: 'italic',
    },
    {
      path: './Roboto-Bold.woff2',
      weight: '700',
      style: 'normal',
    },
    {
      path: './Roboto-BoldItalic.woff2',
      weight: '700',
      style: 'italic',
    },
  ],
})
```

> [!hint] 
> ## [Preloading](https://nextjs.org/docs/basic-features/font-optimization#preloading)
> When a font function is called on a page of your site, it is not globally available and preloaded on all routes. Rather, the font is only preloaded on the related route/s based on the type of file where it is used:
> -   if it's a [unique page](https://nextjs.org/docs/basic-features/pages), it is preloaded on the unique route for that page
>   -   if it's in the [custom App](https://nextjs.org/docs/advanced-features/custom-app), it is preloaded on all the routes of the site under `/pages` 

> [!hint] 
> ## [Reusing fonts](https://nextjs.org/docs/basic-features/font-optimization#reusing-fonts)
> Every time you call the `localFont` or Google font function, that font is hosted as one instance in your application. Therefore, if you load the same font function in multiple files, multiple instances of the same font are hosted. In this situation, it is recommended to do the following:
> -   Call the font loader function in one shared file
>   -   Export it as a constant
>     -   Import the constant in each file where you would like to use this font 




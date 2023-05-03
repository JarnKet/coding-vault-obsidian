>ເປັນການໃຊ້ Theme Switcher ໃນການປ່ຽນຄຸນລັກສະນະໜ້າຕາຂອງເວັບໄຊທ໌ ທີ່ພັດທະນາດ້ວຍ Next.js.

## 1. ການຕິດຕັ້ງດ້ວຍ package

```shell
$ npm install next-themes
# or
$ yarn add next-themes
```
## 2. ການນຳໃຊ້

### 2.1 ການ import ເຂົ້າມາໃຊ້ງານ

> import ເອົາ ThemeProvider ເຂົ້າມາໃຊ້ງານ ແລ້ວນຳເອົາມາຄອບຕົວ <Component {...pageProps} />

```jsx
// src/_app.js
import { ThemeProvider } from 'next-themes';
import Script from 'next/script';
import '../styles/globals.scss';

function MyApp({ Component, pageProps }) {
	return (
		<>
			<ThemeProvider enableSystem={true} attribute="class">
				<Layout>
					<Component {...pageProps} />
				</Layout>
			</ThemeProvider>
		</>
	);
}
export default MyApp;
```

### 2.2 ການນຳເອົາ theme ແລະ useTheme ເຂົ້າໄປໃຊ້ງານເປັນ Function

> import ເອົາ useTheme ເຂົ້າມາໃຊ້ງານ

```jsx
import { useTheme } from 'next-themes';
```

> ນຳເອົາຕົວ useTheme ມາໃຊ້ງານ, ໂດຍຈະສະຫຼາຍໂຄງສ້າງອອກມາ 3 ຕົວຄື:
> - systemTheme ໝາຍເຖິງ theme ລະບົບຂອງຜູ້ໃຊ້.
> - theme ແມ່ນຄ່າ Theme.
> - setTheme ແມ່ນ Function ໃນການກຳນົດຄ່າ theme.
> ຈາກນັ້ນ, ເອົາຕົວ systemTheme ມາກວດສອບເງື່ອນໄຂ ແລ້ວສົ່ງກັບ Button ທີ່ມີ Function ໃນການກຳນົດ Theme.

```jsx
const Header () => {
	const { systemTheme, theme, setTheme } = useTheme();
	return(
		{
			const currentTheme = theme === 'system' ? systemTheme : theme;
			if (currentTheme === 'dark') {
				return (
					<button onClick = {() => {setTheme('light')}}>Light Mode</button>
				)
			}else{
				return (
					<button onClick = {() => {setTheme('dark')}}>Dark Mode</button>
				)
			}
		}
	)
}
```


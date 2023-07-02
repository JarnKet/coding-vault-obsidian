---
tag: Next.js, JSM
sticker: 1f4c2
---
![[Pasted image 20230507131327.png]]

> ປັດຈຸບັນ Next.js 13 ແມ່ນໄດ້ປ່ຽນໂຄງສ້າງຂອງໂຟເດີ້ໃໝ່ ໂດຍມີການເພີ່ມ app ເຂົ້າມາ, ເຊິ່ງເປັນໂຟເດີ້ຫຼັກໃນການແກ້ໄຂຟາຍຂອງເຮົາ.

# layout.js
ເປັນຟາຍທີ່ໄວ້ກຳນົດໂຄງສ້າງຂອງໜ້າເວັບ ໃຫ້ທຸກໆໜ້າມີໂຄງສ້າງອັນດຽວກັນ

```jsx
export default function Layout({children}){
	return(
		<>
			<html lang='en'>
				<body>
					<NavBar/>
					<main>{children}</main>
					<Footer/>
				</body>
			</html>
			
		</>
	)
}
```
ຈາກ Code ເບື້ອງເທິງ ໝາຍຄວາມວ່າ ທຸກໆໜ້າຈະປະກອບໄປດ້ວຍ Navbar ແລະ Footer ສະເໝີ.

# page.js
ເປັນໜ້າຫຼັກຂອງແອັບເຮົາ, ໃນກໍລະນີນີ້ `page.js` ແມ່ນຢູ່ໃນໂຟເດີ້ `app` ນັ້ນໝາຍເຖິງ `localhost:3000/`

```JSX
// app/page.js
// localhost:3000/

export default function Home({children}){
	return(
		<main>
			<h1>This is Home Page</h1>
		</main>
	)
}
```


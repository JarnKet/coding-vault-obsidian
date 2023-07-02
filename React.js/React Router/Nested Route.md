ເປັນການຈັດການ ເສັ້ນທາງ ຫຼື route ທີ່ຊ້ອນກັນໃຫ້ເປັນລະບົບລະບຽບຫຼາຍຂຶ້ນ.
## ການຈັດການຂັ້ນພື້ນຖານ
```jsx
	<Routes>
        <Route path="/" element={<Home />} />
        <Route path="/blogs" element={<Blog />} />
        <Route path="/blogs/:id" element={<BlogPage />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
        <Route path="*" element={<NotFound />} />
    </Routes>
```
ຈາກ Code ຂ້າງໜຶ່ງຈະສັງເກດເຫັນວ່າເປັນການຈັດການເສັ້ນທາງແບບທົ່ວໄປ ແລ້ວຈະມີຈຸດສັງເກດອີກຢ່າງກໍ່ຄື:
- ທຸກ Route ທີ່ເຮົາກຳນົດແມ່ນຢູ່ໃນ path `'/'`
- Route `:id` ແມ່ນຢູ່ໃນ /blog ອີກເທື່ອ

```jsx
	<Routes>
        <Route path="/">
          <Route index element={<Home />} />
          <Route path="blogs">
            <Route index element={<Blog />} />
            <Route path=":id" element={<BlogPage />} />
          </Route>
          <Route path="about" element={<About />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NotFound />} />
        </Route>
    </Routes>
```
ຈາກນັ້ນ, ນຳເອົາ route ທັງໝົດໄປໄວ້ໃນ route `'/'` ໂດຍມີຂໍ້ຄວນສັງເກດດັ່ງນີ້:
- Route ທີ່ມີ property ເປັນ `index` ແມ່ນໝາຍເຖິງເປັນໜ້າທຳອິດຂອງ route ນັ້ນໆ (ໃນທີ່ນີ້ແມ່ນກຳນົດພາຍໃນ `'/'`)
- ຈາກນັ້ນ,​ ເຮົາກໍ່ເອົາ route :id ທີ່ເປັນ '/blogs/:id' ມາຊ້ອນໄວ້ພາຍໃນ 'blogs' ໄດ້ເລີຍ.
- ໂດຍກຳນົດ index ປົກກະຕິໃຫ້ນຳ.

## ການແບ່ງປັນ Layout
![[Pasted image 20230620221256.png]]
![[Pasted image 20230620221305.png]]
ກ່ອນອື່ນແມ່ນເຮັດການສ້າງ Layout ສະເພາະໃຊ້ໃນໜ້ານັ້ນໆ ແລະ ແບ່ງປັນໃຫ້ກັບໜ້າອື່ນໆ (ໃນທີ່ນີ້ແມ່ນເຮົາຕ້ອງການໃຫ້ສະແດງຜົນທຸກໜ້າທີ່ຢູ່ໃນ `'/blogs/'`)

```jsx
import { Outlet, Link } from "react-router-dom";

const BlogLayout = () => {
  return (
    <div className="container px-20 mx-auto">
      <Link to={`/`} className="mt-10 btn">
        Back
      </Link>
      <Outlet />
    </div>
  );
};

export default BlogLayout;

```
>ຈຸດສັງເກດກໍ່ຄືຈະເປັນ `<Outlet />` ເຊິ່ງມັນໝາຍເຖິງ Component ທີ່ໜ້າອື່ນໆທີ່ເຮົາຕ້ອງການສະແດງຜົນ ຕົວຢ່າງ: ປຸ່ມກັບຄືນ ຈະສະແດງຜົນຢູ່ໜ້າບົດຄວາມທັງໝົດ ແລະ ບົດຄວາມແຕ່ລະໜ້າ ເຊິ່ງ Outlet ນີ້ເອງຈະນຳເອົາແຕ່ລະໜ້າມາຕໍ່ທ້າຍ ປຸ່ມກັບຄືນຂອງເຮົາ.

ຈາກນັ້ນ, ກໍ່ເອົາ BlogLayout ຂອງເຮົາໄປກຳນົດທີ່ App ໂດຍເພີ່ມໃຊ້ທີ່ route ທີ່ເປັນ path ຫຼັກ ເຊິ່ງໃນນີ້ແມ່ນ `'blog'`
```jsx
	<Routes>
        <Route path="/">
          <Route index element={<Home />} />
          <Route path="blogs" element={<BlogLayout />}>
            <Route index element={<Blog />} />
            <Route path=":id" element={<BlogPage />} />
          </Route>
          <Route path="about" element={<About />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NotFound />} />
        </Route>
    </Routes>
```

### ການສົ່ງ context ຜ່ານ outlet

```jsx
import { Outlet, Link } from "react-router-dom";

const BlogLayout = () => {
  return (
    <div className="container px-20 mx-auto">
      <Link to={`/`} className="mt-10 btn">
        Back
      </Link>
      <Outlet context={{greetingMessage : 'Hello Sir'}}/>
    </div>
  );
};

export default BlogLayout;

```
ເຮົາສົ່ງຂໍ້ມູນຜ່ານ context ໃນຮູບແບບຂອງ object


```jsx
import { useOutletContext } from "react-router-dom";

const BlogPage = () => {

	const obj = useOutletContext();

	return (
		<>
			<small>{obj.greetingMessage}</small>
		</>
	)
}
```
![[Pasted image 20230620224527.png]]
## ການນຳເອົາແຕ່ລະ Route ມາສ້າງເປັນ Route.js
ເພື່ອຄວາມເປັນລະບຽບ ແລະ ຫຼຸດຄວາມຊັບຊ້ອນພາຍໃນ App.js
```jsx
import { Route, Routes } from "react-router-dom";
import { Blog, BlogPage, BlogLayout } from "./index";

const BlogRoutes = () => {
  return (
    <>
      <Routes>
        <Route element={<BlogLayout />}>
          <Route index element={<Blog />} />
          <Route path=":id" element={<BlogPage />} />
        </Route>
      </Routes>
    </>
  );
};

export default BlogRoutes;

```
ຈາກນັ້ນ, ກໍ່ນຳເອົາ route ມາກຳນົດພາຍໃນ App
```jsx
const App = () => {
  return (
    <>
      <NavBar />
      <Routes>
        <Route path="/">
          <Route index element={<Home />} />
          <Route path="blogs/*" element={<BlogRoutes />} />
          <Route path="about" element={<About />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NotFound />} />
        </Route>
      </Routes>
    </>
  );
};

export default App;
```
ນຳເອົາ BlogRoutes ມາກຳນົດໃນ path `'blogs/*'` ເຊິ່ງເຄື່ອງໝາຍ * ເປັນການກຳນົດເອົາທຸກໜ້າ.
## ການ Config ຂັ້ນເລີ່ມຕົ້ນ

```jsx
//main.js
import { BrowserRouter } from "react-router-dom";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```
- import BrowserRouter ເຂົ້າມາ ແລະ ນຳມາຄອບ <App/> (ເນື່ອງຈາກວ່າ BrowserRouter ເປັນ Context API).
- ເພາະວ່າເຮົາຕ້ອງການທີ່ຈະຄວບຄຸມການເຮັດວຽກ ແລະ ການເຂົ້າເຖິງຂອງເສັ້ນທາງ (route) ພາຍໃນແອັບເຮົາ.

## Routes ແລະ Route

ຈາກນັ້ນ, ສ້າງໜ້າຕ່າງໆຂຶ້ນມາໄວ້ ເພື່ອເຮັດການທົດສອບ
![[Pasted image 20230618215625.png]]


```jsx
//App.js
import { Routes, Route } from "react-router-dom";
import Home from "./pages/Home";
import Blog from "./pages/Blog";
import About from "./pages/About";
import Contact from "./pages/Contact";
import NavBar from "./components/NavBar";

function App() {
  return (
    <>
      <NavBar />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/blogs" element={<Blog />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </>
  );
}

export default App;

```
- ໃນການກຳນົດ ແລະ ຄວບຄຸມເສັ້ນທາງນັ້ນເຮົາຈະນຳໃຊ້ Routes ມາຄອບເສັ້ນທາງຕ່າງໆໄວ້ພາຍໃນເວັບຂອງເຮົາ.
- ສ່ວນ Route ຈະໝາຍເຖິງ ໜ້າ ຫຼື ເສັ້ນທາງຕ່າງໆຂອງເຮົາ.
- Route ຈະມີ property 2 ຕົວທີ່ສຳຄັນຄື:
	`- path` ໝາຍເຖິງເສັ້ນທາງ ຫຼື url ທີ່ເຮົາຈະກຳນົດໄວ້.
	`- element` ໝາຍເຖິງໜ້າເວັບ ທີ່ເຮົາໄດ້ສ້າງໄວ້.

![[Pasted image 20230618220313.png]]
ແລ້ວລອງກວດສອບປ່ຽນ url ຕາມ path ທີ່ເຮົາໄດ້ກຳນົດໄວ້ໃນ route ກໍ່ຈະເຫັນວ່າມີ  ແຕ່ລະໜ້າຂຶ້ນມາ.

## Link
ເປັນ Component ທີ່ເຂົ້າມາແທນ `<a>` ເພື່ອນຳໃຊ້ຮ່ວມກັນກັບ `react-router-dom`

ສ່ວນໃຫ່ຍຈະມີການນຳໃຊ້ຮ່ວມກັບ Navigation Bar

```jsx
import {Link} from 'react-router-dom';

const Navbar = () => {
	return (
		<nav>
			<Link to={`/`}>Home</Link>
			<Link to={`/about`}>About</Link>
			<Link to={`/blogs`}>Blog</Link>
			<Link to={`/contact`}>Contact</Link>
		</nav>
	)
}
```

ໂດຍ Link ຈະມີລັກສະນະການເຮັດວຽກຄ້າຍຄືກັບ a tag ທັງໝົດ ພຽງແຕ່ວ່າມີການປ່ຽນຈາກ `href` ມາເປັນ `to` = ເສັ້ນທາງທີ່ເຮົາກຳນົດໄວ້ໃນ App, ພຽງເທົ່ານີ້ເຮົາກໍ່ສາມາດນຳໃຊ້ເປັນລິ້ງໄດ້ແລ້ວ.
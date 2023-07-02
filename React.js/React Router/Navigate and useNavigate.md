ເປັນຕົວຈັດການການນຳທາງ ໄປຍັງໜ້າອື່ນໆເມື່ອເກີດເຫດການນັ້ນໆ.
## ການນຳທາງຜູ້ໃຊ້ກັບໄປໜ້າຫຼັກ ເມື່ອຜູ້ໃຊ້ເຂົ້າລິ້ງທີ່ບໍ່ຖືກຕ້ອງ

```jsx
const App = () => {
  const element = useRoutes([
    {
      path: "/",
      element: <NavBar />,
      children: [
        // ohter routes...
        {
          path: "*",
          element: <NotFound />,
        },
      ],
    },
  ]);

  return <>{element}</>;
};
```

```jsx
import {Navigate} from 'react-router-dom'

const NotFound = () => {
	return (
		<>
			<Navigate to={`/`} />
		</>
	)
}

export default NotFound;
```
- import Navigate ເຂົ້າມາໃຊ້.
- ເມື່ອ Component ຕົວນີ້ຖືກ Render ຈະສົ່ງຜູ້ໃຊ້ກັບໄປໜ້າທຳອິດທັນທີດ້ວຍ `<Navigate />`
## ການນຳໃຊ້ useNavigate
`>useNavigate` ເປັນ function ທີ່ເຮັດໜ້າທີ່ໃນການນຳທາງຜູ້ໃຊ້ໄປໃນທາງໃດໜຶ່ງ ເຊິ່ງແຕກຕ່າງ `Navigate` ທີ່ເປັນ Component ແລະ ມີຄວາມສາມາດທີ່ຫຼາຍກວ່າ.

### ການນຳທາງຜູ້ໃຊ້ກັບໄປໜ້າທຳອິດ ຫຼັງຈາກ 1 ວິນາທີທີ່ເຂົ້າໜ້າຜິດ

```jsx
import {useNavigate} from 'react-router-dom';
import {useEffect} from 'react';

const NotFound = () => {
	const navigate = useNavigate();
	
	useEffect(()=>{
		setTimeout(() => {
		    navigate(`/`);
	    }, 1000);
	})
	
	return(
		<section>
			<h1>Not Found!</h1>
		</section>
	)

}
```

`>useNavigate` ສ່ວນໃຫ່ຍຈະໃຊ້ນຳທາງຜູ້ໃຊ້ໄປຫາໜ້າໃດໜຶ່ງພາຍໃນເວັບໄຊທ໌ ເມື່ອເກີດເຫດການໃດໜຶ່ງເຊັ່ນ: ຜູ້ໃຊ້ປ້ອນຂໍ້ມູນລັອກອິນສຳເລັດ ແລະ ກໍ່ນຳພາໄປໜ້າຫຼັກ ເປັນຕົ້ນ.
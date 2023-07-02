ເປັນການຈັດການກັບຫຼາຍໆໜ້າທີ່ບໍ່ຊ້ຳກັນ (ຕົວຢ່າງ: ໜ້າບົດຄວາມ ຫຼື ໂປຟາຍຕ່າງໆທີ່ບໍ່ຊ້ຳກັນ)
## Config

```jsx
<Routes>
	//Other Route...
	<Route path="/blogs/:id" element={<BlogPage />} />
</Routes>

```
- ກຳນົດ Route ແບບປົກກະຕິ ແລະ ທີ່ກຳນົດເພີ່ມເຕີມຄື `path` ທີ່ເປັນ `:id`.
- ນັ້ນໝາຍຄວາມວ່າເຮົາຈະກຳນົດໃຫ້ `route` ນີ້ເປັນແບບ dynamic ອີງຕາມ id ທີ່ເຮົາກຳນົດໄວ້.

ຈາກນັ້ນ, ໃຫ້ໄປ Config ທີ່ element ທີ່ເຮົາຕ້ອງການສະແດງຜົນເປັນແບບ Dynamic

```jsx
import { useParams } from "react-router-dom";

const BlogPage = () => {
  const { id } = useParams();
  return <div>BlogPage {id}</div>;
};

export default BlogPage;

```
- import `useParams` ເຂົ້າມາຈາກ `react-router-dom` ເຊິ່ງເປັນຕົວທີ່ໄວ້ຮັບ `:id` ທີ່ໄດ້ກຳນົດໄວ້ໃນ `route.`
- ສ້າງຕົວ id ທີ່ໄດ້ມາຈາກການສະກັດຕົວປ່ຽນ ໂດຍການເອີ້ນໃຊ້ `useParams()`
- ຈາກນັ້ນກໍ່ນຳເອົາມາສະແດງຜົນ.

## ການເຂົ້າເຖິງ

```jsx
<Link className="linkHover" to={`/blogs/1`} />
```
![[Pasted image 20230619104755.png]]
ພຽງເທົ່ານີ້ ກໍ່ສາມາດເຮັດເປັນ Dynamic Page ໄດ້ແລ້ວ.
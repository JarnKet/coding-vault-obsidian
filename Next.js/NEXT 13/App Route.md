---
tag: Next.js, JSM
---
# Routes
ເປັນການກຳນົດ Path ຂອງເວັບແອັບເຮົາ, ເຊິ່ງ Next.js ນັ້ນຈະຈັດການຕົວ route ດ້ວຍໂຟເດີ້ທີ່ຖືກສ້າງພາຍໃນ `app`
![[Pasted image 20230507140053.png]]

```jsx
// app/blog/page.js
// localhost/3000/blog/

const blog = () => {
  return <div>All blog</div>;
};

export default blog;
```
> ເຊິ່ງຈະມີຈຸດສັງເກດຢູ່ເລັກນ້ອຍຢູ່ທີ່ ໂຟເດີ້ທີ່ເປັນ Dynamic Route ແມ່ນຈະຖືກຕັ້ງຊື່ພາຍໃນເຄື່ອງໝາຍ `[]` ແລະ ພາຍໃນຟາຍ `page.js` ຕົວຂ້ໍມູນທີ່ນຳມາສະແດງຜົນກໍ່ຈະຢູ່ພາຍໃຕ້ເຄື່ອງໝາຍ `{}`

# ສ່ວນເພີ່ມເຕີມ
## Route Layout UI

ນອກນີ້,​ ເຮົາຍັງສາມາດສ້າງ Layout ສະເພາະ Route ໄດ້ເພື່ອກຳນົດລັກສະນະສະເພາະໃຫ້ກັບ Route ນັ້ນໆ.
![[Pasted image 20230507142644.png]]

```jsx
const layout = () => {
  return <div>To Top Button</div>;
};

export default layout;
```
ຕົວ Code ຂ້າງເທິງນັ້ນ ແມ່ນຈະສະແດງຜົນໃນສະເພາະທີ່ຢູ່ໃນ Route `/app/blog/`
## Loading Component
ແລະ ແນ່ນອນເຮົາຍັງສາມາດສ້າງ Loading Component ໄດ້ອີກດ້ວຍ ໃນກໍລະນີທີ່ໜ້າເວັບຍັງໂຫຼດບໍ່ທັນສຳເລັດ.

```js
const Loading = () => {
  return <Loading />;
};

export default Loading;
```
## ການຈັດການກັບ Error
ພາຍໃນ Next.js 13 ເຮົາສາມາດສ້າງ Custom Error ໄດ້ດ້ວຍຕົນເອງ ແລະ ຍັງສາມາດ `reset` ໄດ້ດ້ວຍຕົວມັນເອງ

```jsx
'use-client'; // Error Component must be client components

import { useEffect } from 'react';

const Error = ({ error, reset }) => {
  useEffect(() => {
    console.error(error);
  }, [error]);

  return (
    <div>
      <h2>Something Went Wrong</h2>
      <button onClick={reset}>Try Again</button>
    </div>
  );
};

export default Error;
```
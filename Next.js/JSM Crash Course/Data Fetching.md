---
tag: Next.js, JSM
---
> Data Fetching ໝາຍເຖິງການດຶງຂໍ້ມູນຜ່ານ API ມາສະແດງຜົນ, ພາຍໃນ Next.js ມີການດຶງຂໍ້ມູນຢູ່ 3 ປະເພດຄື:
> 1. Server  Side Rendering (SSR)
> 2. Static Side Generation (SSG)
> 3. Incremental Side Rendering (ISR)

# 1. Server Side Rendering (SSR)
ເປັນການດຶງຂໍ້ມູນທາງ Server, ໂດຍຈະມີການດຶງຂໍ້ມູນໃໝ່ທຸກຄັ້ງເມື່ອມີການ Request ຈາກຜູ້ໃຊ້. ເໝາະສຳລັບຂ້ໍມູນທີ່ມີການປ່ຽນແປງຕະຫຼອດເວລາ ເພື່ອທີ່ຕ້ອງການດຶງຂໍ້ມູນມາສະແດງຜົນແບບ Real Time.

```jsx
const post = async ({ params }) => {

  const res = await fetch(
    'https://jsonplaceholder.typicode.com/posts/' + params.postid,
    { cache: 'no-store' }
  );

  const data = await res.json();

  return (
    <div>
      <h1>{data.title}</h1>
      <p>{data.body}</p>
    </div>
  );
};

export default post;
```
ເຮົາມີການ fetch ຂໍ້ມູນແບບປົກກະຕິ, ແຕ່ວ່າໃຫ້ສັງເກດທີ່ `{ cache: 'no-store' }` ໝາຍເຖິງການດຶງຂໍ້ມູນແບບນີ້ ຈະບໍ່ມີການເກັບຂໍ້ມູນລົງພາຍໃນຕົວເຄື່ອງຜູ້ໃຊ້.
# 2. Static Side Generation (SSG)
ເປັນການດຶງຂໍ້ມູນເມື່ອມີການ Build ຕົວລະບົບ, ເໝາະສຳລັບການດຶງຂໍ້ມູນແບບຄົງທີ່ ທີ່ບໍ່ມີການປ່ຽນແປງເປັນປະຈຳເຊັ່ນ: ເນື້ອຫາຂອງ Blog ເປັນຕົ້ນ.
```jsx
const post = async ({ params }) => {

  const res = await fetch(
    'https://jsonplaceholder.typicode.com/posts/' + params.postid,
  );

  const data = await res.json();

  return (
    <div>
      <h1>{data.title}</h1>
      <p>{data.body}</p>
    </div>
  );
};

export default post;
```
ການດຶງຂໍ້ມູນແບບ SSG ແມ່ນຈະບໍ່ໄດ້ກຳນົດຫຍັງລົງໄປເລີຍ ຫຼື ເວົ້າງ່າຍໆວ່າເປັນຄ່າ Default ຂອງ Next.js
# 3. Incremental Side Rendering
ເປັນການນຳຂໍ້ດີຂອງ SSR ແລະ SSG ເຂົ້າມາໄວ້ດ້ວຍກັນ ໂດຍຈະມີການເຮັດວຽກຄື ຈະມີການ Fetch ຂ້ໍມູນຕອນ Build ພ້ອມກັບເກັບລົງເຄື່ອງຜູ້ໃຊ້ ແລະ ຫຼັງຈາກນັ້ນຜ່ານໄປໄລຍະເວລາໃດໜຶ່ງ ກໍ່ຈະ Fetch ຂໍ້ມູນມາອີກຄັ້ງເພື່ອໃຫ້ໄດ້ຂໍ້ມູນແບບ Real Time.
```jsx
const post = async ({ params }) => {

  const res = await fetch(
    'https://jsonplaceholder.typicode.com/posts/' + params.postid,
    {next: {revalidate: 10}}
  );

  const data = await res.json();

  return (
    <div>
      <h1>{data.title}</h1>
      <p>{data.body}</p>
    </div>
  );
};

export default post;
```
ການທີ່ຈະກຳນົດການ Fetch ຂໍ້ມູນແບບນີ້ແມ່ນຈະໄດ້ໃຊ້ `{next: {revalidate: 10}}` ເຂົ້າມາ.
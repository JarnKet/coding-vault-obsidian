---
tag: Next.js, JSM
---
>ໂດຍປົກກະຕິແລ້ວ ຖ້າເຮົາຕ້ອງການພັດທະນາເວັບແອັບແບບ Full Stack ເຮົາຈຳເປັນຕ້ອງໄດ້ດາວໂຫຼດແພັກເກດເສີມຕ່າງໆ ເຊັ່ນ: Express.js, Fastify ເປັນຕົ້ນເພື່ອໃສ່ໃນການຈັດການກັບຖານຂໍ້ມູນຜ່ານ API.
>ແຕ່ວ່າໃນປັດຈຸບັນ Next.js 13 ໄດ້ຮອງຮັບການເຮັດ Backend ໄດ້ແລ້ວ ໂດຍທີ່ບໍ່ຈຳເປັນຕ້ອງເພິ່ງແພັກເກດເສີມຕົວອື່ນເລີຍ ໂດຍການໃຊ້ `route.js`
# route.js
ເປັນໜຶ່ງໃນຟາຍພິເສດຂອງ Next.js 13 (loading, error, layout...) ທີ່ມີໜ້າທີ່ເກັບຕົວ Function ທີ່ໄວ້ກັບ Backend API ໂດຍທີ່ບໍ່ຈຳເປັນຕ້ອງເພິ່ງຕົວແພັກເກດເສີມອື່ນໆ.

```js
export async function GET(request) {

  // Handle GET request for /api/users
  // Retrieve the users from the database or any data source
  const users = [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
    { id: 3, name: 'Joe' },
  ];  
  //Send the users as a response
  return new Response(JSON.stringify(users));

}
```
ນີ້ແມ່ນຕົວຢ່າງໃນການສ້າງ Function ໃນການຈັດການກັບ HTTP Method ໃນການຮ້ອງຂໍຂໍ້ມູນ ດ້ວຍ GET.
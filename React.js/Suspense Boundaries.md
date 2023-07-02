> Suspense Boundaries ເປັນຄວາມສາມາດໜຶ່ງຂອງ React ເວີຊັ້ນ 16 ຂຶ້ນໄປໂດຍມີໜ້າທີ່ໃນການກຳນົດວ່າ Component ຫຼື ຊຸດຄຳສັ່ງໃດທີ່ມີການດຶງຂໍ້ມູນຈາກພາຍນອກ ແລ້ວໃນລະຫວ່າງທີ່ກຳລັງໂຫຼດຂໍ້ມູນນັ້ນ ຕົວ Suspense Boundaries ຈະເຮັດໜ້າທີ່ໃນການສະແດງຜົນ UI ທີ່ບົ່ງບອກຜູ້ໃຊ້ວ່າ ຕອນນີ້ລະບົບກຳລັງດຶງຂໍ້ມູນຢູ່.

# ການໃຊ້ງານ

```jsx

import React, { Suspense } from 'react';
import { fetchData } from './api'; // an async function that fetches data

const MyComponent = () => {
  const data = fetchData(); // an asynchronous call to fetch data

  return (
    <div>
      {data ? data.map(item => <div key={item.id}>{item.title}</div>) : 'Loading...'}
    </div>
  );
};

const App = () => {
  return (
    <div>
      <h1>My App</h1>
      <Suspense fallback={<div>Loading...</div>}>
        <MyComponent />
      </Suspense>
    </div>
  );
};

export default App;

```
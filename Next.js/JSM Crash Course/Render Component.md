---
tag: Next.js, JSM
---
> ປົກກະຕິແລ້ວທຸກໆຢ່າງພາຍໃນ Next.js ແມ່ນຈະຖືກ Render ພາຍໃນຕົວ Server, ແຕ່ວ່າຫຼັງຈາກ React v18 ອອກມາເຮັດໃຫ້ມີການແຍກ Component ອອກມາວ່າຄວນ Render ຝ່າຍໃດ. ພາຍໃນ Next.js 13 ເຮົາສາມາດກຳນົດໄດ້ເອງແບບງ່າຍໆ

![[Pasted image 20230507144122.png]]

# Client Component
ເປັນ Component ທີ່ຈະຖືກ Render ຢູ່ທີ່ຝັ່ງ Client ເໝາະສຳລັບ Component ທີ່ມີການປະຕິສຳພັນໂດຍກົງກັບຜູ້ໃຊ້ ເຊັ່ນ:​ ປຸ່ມ ຫຼື State ຕ່າງໆ. ເຮົາສາມາດກຳນົດໄດ້ໂດຍການປະກາດ `'use-client'` ຢູ່ເທິງສຸດຂອງຟາຍ Component.

```jsx
'use client';
 
import { useState } from 'react';
 
export default function Counter() {
  const [count, setCount] = useState(0);
 
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```
![[Pasted image 20230507144524.png]]
ສາເຫດທີ່ຕ້ອງກຳນົດ `'use-client'` ກໍ່ເພື່ອຫຼຸດ error ທີ່ເກີດຂຶ້ນຝັ່ງ server ແລະ ຍັງເພີ່ມໃຫ້ປະສິດທິພາບຂອງເວັບໃຫ້ດີຂຶ້ນ.
# Server Component
ຈະເປັນ Component ທີ່ຖືກປະມວນຜົນ ຫຼື Render ຢູ່ທີ່ຝັ່ງ Server ເຊິ່ງສຳລັບການເຮັດ Backend ເຊັ່ນ:​ ການໂຫຼດຂໍ້ມູນຕ່າງໆຈາກ Server. ເຊິ່ງ Server Component ຈະບໍ່ມີການກຳນົດຫຍັງພາຍໃນຕົວ Code ໝາຍຄວາມວ່າຖ້າບໍ່ກຳນົດຫຍັງ ນັ້ນແມ່ນ Server Component.

ແລ້ວເມື່ອໃດເຮົາຈະໃຊ້ Server ຫຼື Client Component, ອີງຕາມເວັບໄຊທ໌ ໂດຍກົງຂອງ Next.js ແມ່ນໄດ້ອະທິບາຍໄວ້ດັ່ງນີ້:
![[Pasted image 20230507145831.png]]
Source: https://nextjs.org/docs/getting-started/react-essentials
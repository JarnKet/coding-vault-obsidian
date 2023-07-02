> ເປັນ package ທີ່ໃຊ້ສ້າງ id ແບບສຸ່ມ ໂດຍມີຄ່າເປັນແບບ 128bit ເຊິ່ງເໝາະສຳລັບການສ້າງໄອດີໃຫ້ກັບວັດຖຸ ຫຼື ຂໍ້ມູນແຕ່ລະຢ່າງ.

resource: [uuid - npm (npmjs.com)](https://www.npmjs.com/package/uuid)
# 1. ການຕິດຕັ້ງ

```bash
npm i uuid
```
# 2. ການໃຊ້ງານ

```jsx
import { v4 as uuidv4 } from 'uuid';
uuidv4(); // ⇨ '9b1deb4d-3b7d-4bad-9bdd-2b0d7b3dcb6d'
```
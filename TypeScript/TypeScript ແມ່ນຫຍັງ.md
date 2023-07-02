# TypeScript ແມ່ນຫຍັງ
> TypeScript ເປັນພາສາ JavaScript ແບບ Open Source ທີ່ຖືກພັດທະນາໂດຍບໍລິສັດ Microsoft

- ມີການເພີ່ມຄວາມສາມາດບາງຢ່າງເຂົ້າໄປ ໃຫ້ພາສາ JavaScript ເຊັ່ນ Static Types.
- ການໃຊ້ຊະນິດຂໍ້ມູນ ຫຼື Type ແມ່ນເປັນອີກຕົວເລືອກໜຶ່ງທີ່ສາມາດໃຫ້ເລືອກໃຊ້ໄດ້.
- ມີການ Compile ໄປດ້ວຍພາສາ JavaScript.
- ສາມາດນຳໃຊ້ທັງຝັ່ງ Frontend ແລະ Backend.
- ປະກອບໄປດ້ວຍຄວາມສາມາດຕ່າງໆຈາກມາດຕະຖານ ES6 ແລະ ES7 (Classes, Arrow Function ແລະ ອື່ນໆ).
- Types from 3rd party libraries can be added with type definitions.
# Dynamic vs Static Typing
> ພາສາ Programming ແມ່ນຈະຖືກແບ່ງອອກເປັນ 2 ປະເພດຄື: Dynamically typed languages ແລະ statically typed languages.

- **Dynamically typed languages** ແມ່ນພາສາປະເພດທີ່ບໍ່ໄດ້ກຳນົດຊະນິດຂໍ້ມູນ ເມື່ອມີການປະກາດຕົວແປ ໃນເວລາຂຽນ Code. (Java, C, C++, Rust, Go)
- **Statically typed languages** ແມ່ນພາສາປະເພດທີ່ຕ້ອງໄດ້ກຳນົດຊະນິດຂອງຂໍ້ມູນ ບໍ່ວ່າຈະເປັນຕົວປ່ຽນ,​ parameter ຂອງ function ແລະ ຄ່າຈະ return ອອກໄປ. (JavaScript, Python, Ruby, PHP)
# ຂໍ້ດີ ແລະ ຂໍ້ເສຍ ຂອງ TypeScript
## ຂໍ້ດີ
- ມີຄວາມສາມາດສູງ.
- ຫາ Bug ໄດ້ງ່າຍ.
- ຄາດເດົາຄວາມເປັນໄປໄດ້ງ່າຍ.
- ອ່ານງ່າຍ.
- ເປັນທີ່ນິຍົມ.
## ຂ້ໍເສຍ
- ຂຽນ Code ຫຼາຍຂຶ້ນ.
- ຮຽນຫຼາຍຂຶ້ນ.
- ຈຳເປັນຕ້ອງມີການ Compile.
- ບໍ່ແມ່ນ Static Type ທີ່ແທ້ຈິງ.
# ການ Compile ຂອງພາສາ TypeScript
- ພາສາ TypeScript ແມ່ນໃຊ້ນາມສະກຸນເປນ `.ts` ແລະ `.tsx`
- TSC (TypeScript Compiler) ແມ່ນໃຊ້ສຳລັບການ Compile `.ts` ໄປເປັນ `.js`
- ສາມາດກວດສອບ ແລະ ລາຍງານຂໍ້ຜິດພາດໄດ້ ເວລາມີການ Compile.
- ຫຼາຍໆເຄື່ອງມືແມ່ນຮອງຮັບການ Compile ຂອງພາສາ TypeScript.
- IDE ສ່ວນໃຫ່ຍແມ່ນສາມາດຮອງຮັບພາສາ TypeScript ເປັນຢ່າງດີ.
- ຟາຍ tsconfig.json ແມ່ນໃຊ້ເພື່ອປັບແຕ່ງແກ້ໄຂການເຮັດວຽກຂອງພາສາ TypeScript.
> ເປັນໜຶ່ງໃນຄວາມສາມາດຂອງພາສາ TypeScript ທີ່ສາມາດກຳນົດໂຄງສ້າງຊະນິດຂໍ້ມູນແຕ່ລະ key ຂອງ Objects ໄດ້.

`interface Name {key1 : dataType, ...}`

```ts
interface Person {
	name : string,
	id : number,
	age : number
}

const user1 : Person = {
	name : "Ketsadaphone",
	id : 19401002,
	age : 21
}

console.log(user1.name);  //Ketsadaphone
```
# function interface
> ເປັນການກຳນົດໂຄງສ້າງຊະນິດຂໍ້ມູນໃຫ້ກັບ parameter ຂອງ function


```ts
interface MathFuc{
	(x : number, y : number) : number
}
```
Code ຂ້າງເທິງແມ່ນເປັນການກຳນົດໂຄງສ້າງຊະນິດຂໍ້ມູນຂອງຟັງຊັ້ນຄະນິດສາດໜຶ່ງ ທີ່ຮັບຄ່າ x ແລະ y ເປັນຊະນິດຂໍ້ມູນແບບຕົວເລກ ແລະ ຍັງສົ່ງຄ່າກັບອອກໄປເປັນຕົວເລກ.

```ts
let addFuc: MathFuc = (x: number, y: number) => x + y;
let subFuc: MathFuc = (x: number, y: number) => x - y;

console.log(addFuc(1, 2));  //3
console.log(subFuc(1, 2));  //-1
```
# ການກຳນົດຄຸນລັກສະນະພິເສດໃຫ້ກັບ Key ຂອງ Interface
## 1. readonly
> ຖ້າຫາກວ່າມີການກຳນົດ readonly ທາງໜ້າຊື່ key ຕົວນັ້ນຈະບໍ່ສາມາດແກ້ໄຂຂໍ້ມູນໄດ້ພາຍຫຼັງ

`interface Name {readonly key1 : dataType, ...}`

```ts
interface Person {
	name : string,
	readonly id : number,
	age : number
}

const user1 : Person = {
	name : "Ketsadaphone",
	id : 19401002,
	age : 21
}

user1.id = 12345 //Error!
```
## 2. not required
> ເປັນການກຳນົດໃຫ້ key ຕົວນັ້ນ ສາມາດມີຂໍ້ມູນກໍ່ໄດ້ ຫຼື ບໍ່ມີກໍ່ໄດ້ເມື່ອມີການ ສ້າງ Object ໂດຍອ້າງອີງຈາກ Interface

`interface Name {key? : dataType, ...}`

```ts
interface Person {
	name : string,
	readonly id : number,
	age? : number
}

const user1 : Person = {
	name : "Ketsadaphone",
	id : 19401002,
	age : 21
}

const user2 : Person = {
	name : "Bounthanom",
	id : 1234
}

```
# ບໍ່ສາມາດນຳໃຊ້ໄດ້ກັບຊະນິດຂໍ້ມູນທີ່ເປັນ unions
> interface ບໍ່ສາມາດກຳນົດໂຄງສ້າງຂອງຕົວປ່ຽນທີ່ມີຊະນິດຂໍ້ມູນແບບ union.​ ສະນັ້ນເຮົາຄວນໃຊ້ type ແທນທີ່ສາມາດກຳນົດໄດ້ຢ່າງອິດສະຫຼະ.

```ts
interface Message = string | number   //Error!

type Name = string | number
```
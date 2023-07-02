> ພາສາ TypeScript ຈະມີຊະນິດຂໍ້ມູນຄືກັບພາສາ JavaScript ທັງໝົດເລີຍ ພຽງແຕ່ວ່າໃນການຂຽນ Code ນັ້ນຈະຕ້ອງໄດ້ມີການກຳນົດຊະນິດຂໍ້ມູນລົງໄປນຳ.

# Basic Types
> `let variableName: dataType = value`

```ts
let id: number = 1;

let fullName: string = "Ketsadaphone BOUTPANYDA";

let isHuman: boolean = true;

let bio: any = "Hello World";

bio = 16;
```
> ແຕ່ວ່າໃຫ້ສັງເກດບ່ອນທີ `any` ເປັນ keyword ທີ່ໃຊ້ກຳນົດວ່າ ຕົວປ່ຽນນັ້ນຈະເປັນຊະນິດຂໍ້ມູນແບບໃດກໍ່ໄດ້ ແລະ ສາມາດກຳນົດໃໝ່ເປັນຄ່າໃໝ່ຊະນິດຂໍ້ມູນໃໝ່.
 
# Array
> Array ເປັນຊະນິດຂໍ້ມູນທີ່ຈັດເກັບຂໍ້ມູນຫຼາຍຕົວທີ່ມີຊະນິດຂໍ້ມູນອັນດຽວກັນ ເໝາະສຳລັບການຈັດເກັບຂ້ໍມູນຂະໜາດໃຫ່ຍ ແລະ ສາມາດແກ້ໄຂໄດ້ພາຍຫຼັງ.

`> let variableName: dataType[] = [values,.....]`
```ts
let employee: string[] = ["Bob", "Sally", "Sam"];

let employee2: Array<string> = ["Bob", "Sally", "Sam"];

let randomData: any[] = ["Bob", 1, "Sally", 2, "Sam", true];
```
# Tuple
> Tuple ເປັນຊະນິດຂໍ້ມູນທີ່ຈັດເກັບຂໍ້ມູນຫຼາຍຕົວທີ່ມີຊະນິດແຕກຕ່າງກັນໄດ້ ເໝາະສຳລັບການຈັດເກັບຂໍ້ມູນຂະໜາດນ້ອຍ ແຕ່ວ່າບໍ່ສາມາດແກ້ໄຂໄດ້.

`> let variableName: [dataTypes,...] = [value]`
```ts
let ketsadaphone: [number, string] = [1, "ketsadaphone"];
```
## Tuple Array
`> let variableName: [dataTypes,...][] = [[value],...]`

```ts
let employee: [number, string, boolean][];

employee = [
  [1, "ketsadaphone", true],
  [2, "John Doe", false],
  [3, "Will", true],
];
```
# union
> ເປັນໜຶ່ງໃນຊະນິດຂໍ້ມູນພິເສດທີ່ສຳຄັນ ໃນພາສາ TypeScript ເຊິ່ງເຮັດໃຫ້ສາມາດກຳນົດຕົວປ່ຽນ ທີ່ມີຊະນິດຂໍ້ມູນ 2 ແບບຂຶ້ນໄປໄດ້.

`let id: string | number;`

```ts
let id: number | string;

id = 19401002;
console.log(typeof id);  //valid | number

id = "19401002";
console.log(typeof id);  //valid | string

id = true;
console.log(typeof id);  //invalid | error
```
# enum
> ເປັນອີກໜຶ່ງໃນຊະນິດຂໍ້ມູນແບບພິເສດທີ່ສຳຄັນໃນ TypeScript ທີ່ເຮັດໃຫ້ເຮົາສາມາດປະກາດຕົວປ່ຽນແບບ ຄ່າຄົງທີ່ ຫຼື Constant ຫຼາຍໆຕົວພ້ອມກັນ

```ts
enum Color {
	red,   //0
	green, //1
	blue,  //2
}

let myColor: Color = Color.Green; 
console.log(myColor); // logs 1
```
ຈາກ Code ຂ້າງເທິງເຮົາໄດ້ມີການສ້າງຕົວປ່ຽນແບບ Constants ຫຼາຍຕົວພ້ອມກັນດ້ວຍ `enums` ແລະ ລອງສະແດງຄ່າ `Color.Green` ພາຍໃນອອກມາ ຈະພົບວ່າ ເປັນ `1`, ສາເຫດກໍ່ຍ້ອນວ່າ ຖ້າເຮົາກຳນົດຕົວປ່ຽນໂດຍທີ່ບໍ່ກຳນົດຄ່າ ຄ່າຂອງຕົວປ່ຽນຈະເປັນຕົວເລກ ໂດຍເລີ່ມຈາກ `0` ຄ້າຍຄືກັບ Array.

```ts

enum Direction {
  Up = "UP",
  Down = "DOWN",
  Left = "LEFT",
  Right = "RIGHT"
}

let myDirection: Direction = Direction.Up;
console.log(myDirection); // logs "UP"

```
ແລະ ແນ່ນອນເຮົາສາມາດກຳນົດຄ່າໃຫ້ກັບຕົວປ່ຽນຂອງເຮົາໄດ້ ແລະ ສາມາດເຂົ້າເທິງແບບປົກກະຕິໄດ້ເລີຍ.
# object
> ເປັນຊະນິດຂໍ້ມູນທີ່ສາມາດຈັດເກັບຂໍ້ມູນໄດ້ຫຼາຍຄ່າທີ່ມີຊະນິດຂໍ້ມູນທີ່ແຕກຕ່າງກັນ ໂດຍກຳກັບດ້ວຍ key


```ts
let user : {
	id: number,
	fName: string,
	age: number
} = {
	id: 19401002,
	fName: 'Ketsadaphone BOUTPANYDA',
	age: 21
}
```
ແຕ່ຈະສັງເກດວ່າ Code ຈະຍາວຫຼາຍເກີນໄປ ເມື່ອມີການປະກາດຕົວປ່ຽນທຸກຕົວແບບນີ້. ສະນັ້ນ,​ ເຮົາສາມາດຫຍໍ້ລົງ ດ້ວຍການປະກາດ Type Interface ແລ້ວນຳໃຊ້ຄັ້ງດຽວໄດ້ເລີຍແບບນີ້:

```ts
type User = {
  id: number;
  fName: string;
  age: number;
};

let Ket : User = {
  id: 19401002,
  fName: "Ketsadaphone BOUTPANYDA",
  age: 21,
};

let Along : User = {
	id: 12345,
	fName: "Bouthanom SOUVANTHONG",
	age: 20,
}
```
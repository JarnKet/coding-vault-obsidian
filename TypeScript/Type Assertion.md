> ເປັນການຢືນຢັນ ຫຼື ລະບຸຊະນິດຂໍ້ມູນຢ່າງຊັດເຈນເມື່ອມີການນຳໃຊ້ກັບ ຊະນິດຂໍ້ມູນແບບ Any

ເຊິ່ງການໃຊ້ Type Assertion ສາມາດເຮັດໄດ້ 2 ວິທີຄື:
1. ການໃຊ້ເຄື່ອງໝາຍ `<>`
2. ການໃຊ້ `as` keyword
# 1. ການໃຊ້ເຄື່ອງໝາຍ <>

```ts
let greetTxt : any = 'Hello';

let greetTxtLength : number = (<string>greetTxt).length;

console.log(greetTxtLength);  // 5
```
> ຈາກ Code ຂ້າງເທິງດັ່ງກ່າວເຮົາໄດ້ມີການສ້າງຕົວປ່ຽນທີ່ເປັນຊະນິດຂໍ້ມູນແບບ `Any`, ແລ້ວສ້າງຕົວປ່ຽນໃໝ່ `greetTxtLength` ທີ່ຕ້ອງການເກັບຕົວເລກ ທີ່ນັບຂະໜາດຕົວອັກສອນ ທີ່ອ້າງອີງມາຈາກ  `greetTxt` ແມ່ນເຮົາຈະໃຫ້ເທົ່າກັບ `(<string>greetText).length` ເພື່ອໃຫ້ສາມາດໃຊ້ method ຕ່າງໆຂອງຊະນິດຕົວປ່ຽນນັ້ນໆ.

# 2. ການໃຊ້ as keyword

```ts
let greetTxt : any = 'Hello';

let greetTxtLength : number = (greetTxt as string).length;

console.log(greetTxtLength);  // 5
```
ແບບນີ້ຈະສັ້ນ ແລະ ເຂົ້າໃຈໄດ້ງ່າຍກວ່າ.

# Function ທີ່ມີການ Return ຄ່າ
`function functionName (parameterN : dataType,...) : dataTypeOfReturnValue` {code...}

```ts
function addTwoNums(x : number, y : number) : number {
	return x + y;
}
```
> ຈາກ Code ດ້ານເທິງເປັນຟັງຊັ້ນໃນການບວກສອງຕົວເລກ ເຊິ່ງຮັບຄ່າ x ແລະ y ທີ່ກຳນົດຊະນິດຂ້ໍມູນເປັນຕົວເລກ ແລະ ຕົວຟັງຊັ້ນກໍ່ຍັງຕ້ອງ Return ຄ່າອອກໄປເປັນຕົວເລກ. ເຊິ່ງສາມາດກຳນົດຊະນິດຂໍ້ມູນສຳລັບຄ່າຂໍ້ມູນທີ່ຈະສົ່ງອອກໄປຫຼັງ Expression ຫຼື ບ່ອນຮັບ Parameter.

# Function ທີ່ບໍ່ມີການ Return ຄ່າ
`function functionName (parameterN : dataType,...) : void {code...}`

```ts
function geetingLog(message : string | number) : void{
	console.log('Hello ' + message)
}
```
> ຈາກ Code ຂ້າງເທິງເປັນຟັງຊັ້ນທີ່ສະແດງຂໍ້ຄວາມທັກທາຍທີ່ຮັບຄ່າ ເຂົ້າມາເປັນຊະນິດຂໍ້ມູນແບບ String ແລະ Number ຫຼື ເອີ້ນວ່າ Union ກໍ່ໄດ້. ເຊິ່ງຟັງຊັ້ນນີ້ຈະບໍ່ມີການສົ່ງຄ່າໃດໆອອກໄປ ເຮົາກໍ່ຈະກຳນົດ void ໄວ້ຫຼັງ Expression ຫຼື ບ່ອນຮັບ Parameter.
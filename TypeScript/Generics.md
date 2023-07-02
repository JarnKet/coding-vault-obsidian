ເປັນການກຳນົດຊະນິດຂໍ້ມູນຂອງສິ່ງໃດໜຶ່ງໃຫ້ຄົງທີ່

```ts
function getArray<Type>(items: Type[]): Type[] {
  return new Array().concat(items);
}

let myNumArr = getArray<number>([100, 200, 300]);

myNumArr.push(400);  //Ok
myNumArr.push("Hello"); // Error
```
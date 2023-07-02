
```ts
class Person {
	name : string
	id : number

	constructor(name : string, id : number){
		this.name = name
		this.id = id
	}
}
```
ເປັນການສ້າງ Class Person ແບບປົກກະຕິທົ່ວໄປຄ້າຍຄືກັບພາສາ JavaScript ເລີຍ.
# 1. ການສ້າງຕົວປ່ຽນຈາກ Class
ການສ້າງຕົວປ່ຽນຈາກ function ກໍ່ສາມາດເຮັດໄດ້ຄືພາສາ JavaScript ທົ່ວໄປ.

```ts
const user1 = new Person('Ketsadaphone', 1);
const user2 = new Person('Bounthanom', 2);
```
# 2. ການເຂົ້າເຖິງຂໍ້ມູນ Data Modifier
## Public
>ເປັນ keyword ທີ່ປະກາດຢູ່ໜ້າຕົວປ່ຽນພາຍໃນ class ເຊິ່ງຖ້າຫາກກຳນົດແລ້ວ ເຮົາຈະສາມາດແກ້ໄຂຕົວປ່ຽນນັ້ນໄດ້ຈາກທຸກບ່ອນ.

```ts
class Person {
	public name : string
	id : number

	constructor(name : string, id : number){
		this.name = name
		this.id = id
	}
}

const user1 = new Person('Ketsadaphone', 1);

user1.name = 'JarnKet';
user1.id = 19401002;
```
ຈະສັງເກດເຫັນວ່າ ເຖິງເຮົາຈະບໍ່ກຳນົດ public ໃຫ້ id ກໍ່ສາມາດເຂົ້າເຖິງ ແລະ ແກ້ໄຂໄດ້ປົກກະຕິ. ສະນັ້ນ, ຖ້າຫາກເຮົາຢາກສາມາດເຂົ້າເຖິງຂໍ້ມູນພາຍໃນ class ໄດ້ເຮົາບໍ່ຕ້ອງກຳນົດ public ຫຼື ຈະກຳນົດກໍ່ໄດ້.
## Protected and Private
> ເປັນ Keyword ທີ່ໃຊ້ໃນການປົກປິດ ແລະ ຈຳກັດການເຂົ້າເຖິງ ຫຼື ແກ້ໄຂຂໍ້ມູນ. ແຕ່ວ່າສາມາດເຂົ້າເຖິງພາຍໃນ Class ດຽວກັນໄດ້.

```ts
class Person {
	private name : string
	protected id : number

	constructor(name : string, id : number){
		this.name = name
		this.id = id
	}
		
	greeting(){
		return `${this.name} says hi to you!`;
	}
}

const user1 = new Person('Ketsadaphone', 1);

user1.name = 'JarnKet'; // Error!
console.log(user1.id) // Error!

console.log(user1.greeting()); //JarnKet says hi to you!
```
# 3. ການຈັດໂຄງສ້າງຂອງ Class ດ້ວຍ Interface
ກ່ອນອື່ນໃຫ້ເຮົາສ້າງ interface ຂຶ້ນມາເສຍກ່ອນ

```ts
interface PersonInterface{
	id : number
	name : string
	greeting() : string
}
```
ຈາກນັ້ນ, ເຮົາມາສ້າງ Class ດ້ວຍການຈັດໂຄງສ້າງຕາມ interface ທີ່ໄດ້ວາງໄວ້ ໂດຍການໃຊ້ keyword `implements`

```ts
class Person implements PersonInterface{
	id : number
	name : string
	
	constructor(name : string, id : number){
		this.name = name
		this.id = id
	}
		
	greeting(){
		return `${this.name} says hi to you!`;
	}
} 
```
# 4. ການສ້າງ Subclass ຫຼື Extends
ກ່ອນອື່ນແມ່ນໃຫ້ສ້າງ Super ເພື່ອເຮັດການສືບທອດຄຸນລັກສະນະ ຈາກນັ້ນກໍ່ມາສ້າງ Subclass ດ້ວຍການໃຊ້ Extends

```ts
class Employee extends Person {
  position: string;

  constructor(id: number, name: string, position: string) {
    super(id, name);
    this.position = position;
  }
}

const MrKet = new Employee(1, "MrKet", "Developer");
```

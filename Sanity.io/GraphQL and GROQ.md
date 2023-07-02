ໃນການດຶງຂໍ້ມູນຈາກ Sanity ນັ້ນເຮົາສາມາດດຶງມັນໄດ້ພາສາ Query ຍຸກໃໝ່ແບບ GraphQL ຫຼື ພາສາທີ່ຖືກພັດທະນາເພື່ອ Sanity ໂດຍສະເພາະນັ້ນກໍ່ຄື GROQ.
>ສາມາດອ່ານເອກະສານເພີ່ມເຕີມໄດ້ກ່ຽວກັບການນຳໃຊ້ພາສາ GROQ: [Query Language (GROQ) - Reference (sanity.io)](https://www.sanity.io/docs/groq-reference)

## ການດຶງຂໍ້ມູນເບື້ອງຕົ້ນ
![[Pasted image 20230630141613.png]]
ໂດຍເຮົາຈະເຂົ້າມາທີ່ studio ແລະ ແຖບເມນູ vision, ຈາກນັ້ນ ຈະສັງເກດເຫັນແຖບເບື້ອງຊ້າຍທີ່ເອົາໄວ້ຂຽນຄຳສັ່ງໃນການດຶງຂໍ້ມູນ

### 1. ການດຶງຂໍ້ມູນທັງໝົດ

```graphql
*[_type == 'schemaName']
```

ເປັນການດຶງເອົາຂໍ້ມູນທັງໝົດ ຫຼື ໃນ entity ທີ່ມີຊື່ວ່າ post ດ້ວຍຄຳສັ່ງ `*[_type == 'post']`
![[Pasted image 20230630141848.png]]

### 2. ການດຶງຂໍ້ມູນສະເພາະ ຂອງຊຸດຂໍ້ມູນແຕ່ລະຕົວ

```graphql
*[_type == 'schemaName']{
	fieldName1,
	filedName2->{
		someProps
	}
}
```
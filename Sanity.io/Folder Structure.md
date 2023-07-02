![[Pasted image 20230630134141.png]]
ໃນ Sanity Project ແມ່ນຈະມີ folder ທີ່ສຳຄັນຄື `schemas` ແລະ ຟາຍ `sanity.config.ts`
## schemas
ເປັນໂຟເດີ້ທີ່ຈັດເກັບຟາຍ ທີ່ເປັນໂຄງສ້າງຂອງບ່ອນເກັບຂໍ້ມູນຂອງເຮົາ (ຄ້າຍຄືກັບຟາຍ table ຂອງຖານຂໍ້ມູນ) ໂດຍຈະຖືກຂຽນເປັນຟາຍນາມສະກຸນ `.ts` ແລະ `.js`

```ts
import {defineField, defineType} from 'sanity'

export default defineType({
  name: 'post',
  title: 'Post',
  type: 'document',
  fields: [
    defineField({
      name: 'title',
      title: 'Title',
      type: 'string',
    }),
    defineField({
      name: 'slug',
      title: 'Slug',
      type: 'slug',
      options: {
        source: 'title',
        maxLength: 96,
      },
    }),
    defineField({
      name: 'author',
      title: 'Author',
      type: 'reference',
      to: {type: 'author'},
    }),
    defineField({
      name: 'mainImage',
      title: 'Main image',
      type: 'image',
      options: {
        hotspot: true,
      },
    }),
    defineField({
      name: 'categories',
      title: 'Categories',
      type: 'array',
      of: [{type: 'reference', to: {type: 'category'}}],
    }),
    defineField({
      name: 'publishedAt',
      title: 'Published at',
      type: 'datetime',
    }),
    defineField({
      name: 'body',
      title: 'Body',
      type: 'blockContent',
    }),
  ],

  preview: {
    select: {
      title: 'title',
      author: 'author.name',
      media: 'mainImage',
    },
    prepare(selection) {
      const {author} = selection
      return {...selection, subtitle: author && `by ${author}`}
    },
  },
})

```
ຈາກ Code ຂ້າງເທິງຈະມີ 2 ສິ່ງທີ່ສຳຄັນຄື: defineType ແລະ defineField ເຊິ່ງມີຄວາມສຳຄັນດັ່ງນີ້:
- defineType ເປັນຕົວສ້າງ entity ຫຼື table ຕ່າງໆ ເຊິ່ງຈະປະກອບໄປດ້ວຍ name, title, type ແລະ field.
- defineField ເປັນຕົວສ້າງ ຟິວ ຫຼື ເຣຄອດ ພາຍໃນ entity ນັ້ນໆ ເຊິ່ງແຕ່ລະ ຟິວ ຈະມີຊະນິດ ແລະ ຄຸນສົມບັດທີ່ແຕກຕ່າງກັນ.
ເຮົາສາມາດອ່ານຊະນິດຂໍ້ມູນຕ່າງໆຜ່ານເວັບນີ້: [Schema (sanity.io)](https://www.sanity.io/docs/schema-types#types-8137822cbda1)

ເຊິ່ງສິ່ງທີ່ເຮົາໄດ້ກຳນົດພາຍໃນຟາຍນັ້ນ ແມ່ນຈະປະກົດຂຶ້ນມາພາຍໃນ studio (ຕົວຈັດການຂໍ້ມູນ) ເມື່ອເຮົາມີການຣັນລະບົບຂຶ້ນມາ
![[Pasted image 20230630135241.png]]
## sanity.config.ts
ເປັນຟາຍທີ່ຈັດເກັບເຄື່ອງມື ຫຼື ການຕັ້ງຄ່າຕ່າງໆ

```ts
import {defineConfig} from 'sanity'
import {deskTool} from 'sanity/desk'

import {schemaTypes} from './schemas'

export default defineConfig({
  name: 'default',
  title: 'sanity_crash_course',

  projectId: 'xhusiu42',
  dataset: 'test',

  plugins: [deskTool()],

  schema: {
    types: schemaTypes,
  },
})

```

ນອກນັ້ນ, ເຮົາຍັງສາມາດຕິດຕັ້ງ plugin ເສີມໄດ້ເພື່ອນຳມາຊ່ວຍໃນການເຮັດຂອງເຮົາງ່າຍຂຶ້ນ, ເຊິ່ງເຮົາຈະຕິດຕັ້ງ plugin ທີ່ມີຊື່ວ່າ vision ທີ່ເປັນພື້ນທີ່ ທີ່ໃຫ້ເຮົາສາມາດທົດລອງຂຽນ code ເພື່ອດຶງຂໍ້ມູນໄດ້.

```shell
npm i @sanity/vision@latest
```

ຈາກນັ້ນ,​ ນຳເອົາ plugin ທີ່ຕິດຕັ້ງມາເພີ່ມໃສ່ໃນຟາຍ config

```ts
import {defineConfig} from 'sanity'
import {deskTool} from 'sanity/desk'      //import ເຂົ້າມາໃຊ້
import {visionTool} from 'sanity/vision'
import {schemaTypes} from './schemas'

export default defineConfig({
  name: 'default',
  title: 'sanity_crash_course',

  projectId: 'xhusiu42',
  dataset: 'test',

  plugins: [deskTool(), visionTool()],  //ນຳເອົາ visionTool ເຂົ້າມາໃສ່

  schema: {
    types: schemaTypes,
  },
})

```
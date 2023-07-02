---
tag: npm-package, React.js, Next.js
---
> ເປັນການກຳນົດ ແລະ ໃສ່ Meta data ໃຫ້ກັບ React App ຂອງເຮົາ.

## ການຕິດຕັ້ງ

```shell
npm install react-helmet
```

## ການນຳໃຊ້

```jsx
//Blog.jsx
// htpp://localhost:3000/blogs

import { Helmet } from "react-helmet";

const Blog = () =>{
	return(
		<>
			<Helmet>
				<title>All Blog</title>
		        <meta name="description" content="Your page description" />
		        <meta name="keywords" content="Your page keywords" />
			</Helmet>
			<div>
				...Content Here
			</div>
		</>
	)
}



```
- import `Helmet` ເຂົ້າມາເພື່ອນຳໃຊ້.
- ນຳເອົາ Tag `Helmet` ເຂົ້າໄປນຳໃຊ້
- ພາຍໃນແມ່ນ ຈະນຳ Tag `title` ແລະ `meta` tag ຕ່າງໆເຂົ້າມາ.
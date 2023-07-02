> ເປັນ library ທີ່ຊ່ວຍໃຫ້ເຮົາສາມາດສ້າງປຸ່ມແຊ ໜ້າເວັບປັດຈຸບັນ ໄປຫາແພັດຟອມ Social Media ອື່ນໆໄດ້ຢ່າງງ່າຍດາຍ.

## installation

```shell
npm i react-share
```

## ການນຳໃຊ້ເບື້ອງຕົ້ນ

```jsx
import {
  FacebookShareButton,
  WhatsappShareButton,
  TwitterShareButton,
} from "react-share";

const url = 'https://someAPI....'

export function ShareButton(){
	return(
		<div>
			<FacebookShareButton url={url}>
				Share to Facebook
			</FacebookShareButton>
			
			<WhatsappShareButton url={url}>
				Share to WhatApps
			</WhatsappShareButton>
			
			<TwitterShareButton url={url}>
				Share to Twitter
			</TwitterShareButton>
		</div>
	)
}

```
- ມີການນຳເອົາ ປຸ່ມຕ່າງໆເຂົ້າມາຈາກ react-share
- ສ້າງ url ຫຼື ລິ້ງທີ່ເຮົາຕ້ອງການ share ໄປຫາແພັດຟອມນັ້ນໆ
- ນຳເອົາປຸ່ມ ມາໃຊ້ງານເປັນ Component ໂດຍມີ `property` ເປັນ `url` ຈາກນັ້ນ,​ ກໍ່ວາງລິ້ງທີ່ຕ້ອງການຈະແຊໄປໜ້າອື່ນ.
## ການແຊໜ້າປັດຈຸບັນໄປຫາແພັດຟອມອື່ນໆ

```jsx
import {useState, useEffect} from 'react';
import {
  FacebookShareButton,
} from "react-share";

export function Post(){
	const [url, setUrl] = useState(undefined);

	useEffect(() => {
	    const getCurrentPageUrl = () => {
	      if (typeof window !== "undefined") {
	        return window.location.toString();
	      }
	      return "";
	    };
	
	    const shareUrl = getCurrentPageUrl();
	    setUrl(shareUrl);
	}, []);

	return(
		<div>
			<h1>This is Post Page</h1>
			<FacebookShareButton url={url}>
				Share to Facebook
			</FacebookShareButton>
		</div>
	)
}

```
- ນຳເອົາ useState ແລະ useEffect ເຂົ້າມາເພື່ອເຮັດການດຶງ path ປັດຈຸບັນ ແລ້ວກຳນົດຄ່າໃຫ້ url.
- ນຳເອົາ window (global variable) ມາກວດສອບ ແລ້ວ `return window.location.toString();` ເຊິ່ງ path url ໜ້າປັດຈຸບັນທີ່ເຮົາຢູ່.
- ຈາກນັ້ນ,​ ກໍ່ເຮັດ set ຄ່າໃຫ້ກັບ url.
- ພຽງເທົ່ານີ້ກໍ່ໄດ້ທີ່ຢູ່ໜ້າທີ່ຕ້ອງການແລ້ວ.
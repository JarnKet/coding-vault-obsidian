ເປັນ Function ທີ່ໄວ້ຄົ້ນຫາເສັ້ນທາງຕ່າງໆພາຍໃນແອັບຂອງເຮົາ.
## ການໄປໜ້າຂອງເວັບ ດ້ວຍການພິມຜ່ານ Input ໂດຍການໃຊ້ useSearchParams

```jsx
import {useSearchParams, useNavigate}

const Blog = () => {
	const [searchParams, setSearchParams] = useSearchParams({id: ''});
	const navigate = useNavigate();
	
	function handleOnClick() {
		navigate(searchParams.get('id'));
	}

	return(
		<section>
			<input
				type='text' 
				placeholder='Blog ID'
				value={searchParams}
				onChange={(e) => e.target.value}
			/>
			<button onClick={handleOnClick}>Search</button>
		</section>
	)
}

export default Blog;
```
![[Pasted image 20230623225416.png]]
![[Pasted image 20230623225426.png]]
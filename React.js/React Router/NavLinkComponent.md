>ເປັນ LinkComponent ທີ່ຖືກອອກແບບມາເພື່ອເຮັດ Navigation Link ໂດຍມີຈຸດເດັ່ນທີ່ສາມາດປັບແຕ່ງ style ເພີ່ມເຕີມໄດ້ເມື່ອເຮົາມີການຄິກ.

## ການໃຊ້ Style ເພີ່ມເຕີມເມື່ອມີການຢູ່ໜ້ານັ້ນໆ
ໂດຍເຮົາຈະນຳໃຊ້ Prop ພິເສດທີ່ມີເຂົ້າມາໃນ NavLink ນັ້ນກໍຄື isActive ເຊິ່ງເປັນຄ່າ boolean ທີ່ຈະກວດສອບວ່າ Link ນັ້ນມີການຖືກກົດ ຫຼື ບໍ່.
```jsx
			<li>
                <NavLink
                  className={({ isActive }) => {
                    return isActive ? "text-primary" : "";
                  }}
                  to={`/about`}
                >
                  About
                </NavLink>
            </li>
            <li>
                <NavLink
                  className={({ isActive }) => {
                    return isActive ? "text-primary" : "";
                  }}
                  to={`/blogs`}
                >
                  Blog
                </NavLink>
            </li>
            <li>
                <NavLink
                  className={({ isActive }) => {
                    return isActive ? "text-primary" : "";
                  }}
                  to={`/contact`}
                >
                  Contact
                </NavLink>
            </li>
```
ເຮົາມີການສ້າງ function ພາຍໃນ className ຂອງ NavLink ໂດຍມີການສະກັດໂຄງສ້າງດຶງເອົາ isActive ມາແລ້ວມາກວດສອບວ່າ ຖ້າຫາກເປັນຈິງກໍ່ເພີ່ມ Style ລົງໄປ.
![[Pasted image 20230621224321.png]]

ນອກນັ້ນ, ຍັງມີອີກ props ໜຶ່ງທີ່ຖືກອອກແບບມາໃຫ້ໃຊ້ງານງ່າຍນັ້ນກໍຄື `activeClassName` ເຊິ່ງຖືກອອກແບບມາເພື່ອໃສ່ສະຕາຍໂດຍສະເພາະ

```jsx
			<li>
              <NavLink activeClassName="active" to={`/about`}>
                About
              </NavLink>
            </li>
            <li>
              <NavLink activeClassName="active" to={`/blogs`}>
                Blog
              </NavLink>
            </li>
            <li>
              <NavLink activeClassName="active" to={`/contact`}>
                Contact
              </NavLink>
            </li>
```
ເຮົາຈະສັງເກດເຫັນວ່າ Code ແມ່ນສັ້ນລົງ ແລະ ພຽງແຕ່ກຳນົດ className ທີ່ເຮົາກຳນົດໄວ້ໃນ CSS ມາໃສ່.
ແຕ່ວ່າມີຈຸດສັງເກດຢູ່ບ່ອນທີ່ວ່າຕົວ ປຸ່ມຈະມີການປ່ຽນສີຕະຫຼອດເວລາ ເມື່ອຢູ່ໃນເສັ້ນທາງດຽວກັນ ສະນັ້ນເຮົາຈະກຳນົດ `end` ໃສ່ເພື່ອໃຫ້ມັນບໍ່ມີແສງ.
![[Pasted image 20230621225544.png]]

```jsx
			<li>
              <NavLink activeClassName="active" to={`/about`}>
                About
              </NavLink>
            </li>
            <li>
              <NavLink activeClassName="active" end to={`/blogs`}>
                Blog
              </NavLink>
            </li>
            <li>
              <NavLink activeClassName="active" to={`/contact`}>
                Contact
              </NavLink>
            </li>
```
![[Pasted image 20230621225726.png]]
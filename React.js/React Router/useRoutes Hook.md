>ເປັນ React Function Hook ທີ່ມານຳ React Router Dom ເຊິ່ງມີໜ້າທີ່ໃນການຈັດການເສັ້ນທາງໃຫ້ສະດວກ ສະບາຍຂຶ້ນອິກ.

ເຮົາຈະປ່ຽນ Route ລຸ່ມນີ້ເປັນການນຳໃຊ້ useRoutes ແທນ
```jsx

const App = () => {
  return (
    <>
      <NavBar />
      <Routes>
        <Route path="/">
          <Route index element={<Home />} />
          <Route path="blogs/*" element={<BlogRoutes />} />
          <Route path="about" element={<About />} />
          <Route path="contact" element={<Contact />} />
          <Route path="*" element={<NotFound />} />
        </Route>
      </Routes>
    </>
  );
};

export default App;

```

ແລະ ຈະມີໂຄງສ້າງດັ່ງນີ້
```jsx
//App.jsx
import { useRoutes } from "react-router-dom";
import { Home, About, Contact, NotFound, BlogRoutes } from "./pages";
import NavBar from "./components/NavBar";

const App = () => {
  const element = useRoutes([
    {
      path: "/",
      element: <NavBar />,
      children: [
        {
          index: true,
          element: <Home />,
        },
        {
          path: "blogs/*",
          element: <BlogRoutes />,
        },
        {
          path: "about",
          element: <About />,
        },
        {
          path: "contact",
          element: <Contact />,
        },
        {
          path: "*",
          element: <NotFound />,
        },
      ],
    },
  ]);

  return <>{element}</>;
};

export default App;

```


```jsx
//BlogRoutes.jsx
import { useRoutes } from "react-router-dom";
import { Blog, BlogPage, BlogLayout } from "./index";

const BlogRoutes = () => {
  const element = useRoutes([
    {
      path: "/",
      element: <BlogLayout />,
      children: [
        {
          index: true,
          element: <Blog />,
        },
        {
          path: ":id",
          element: <BlogPage />,
        },
      ],
    },
  ]);

  return <>{element}</>;
};

export default BlogRoutes;

```


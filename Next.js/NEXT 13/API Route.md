---
tag: Next.js, JSM
---
>ໂດຍປົກກະຕິແລ້ວ ຖ້າເຮົາຕ້ອງການພັດທະນາເວັບແອັບແບບ Full Stack ເຮົາຈຳເປັນຕ້ອງໄດ້ດາວໂຫຼດແພັກເກດເສີມຕ່າງໆ ເຊັ່ນ: Express.js, Fastify ເປັນຕົ້ນເພື່ອໃສ່ໃນການຈັດການກັບຖານຂໍ້ມູນຜ່ານ API.
>ແຕ່ວ່າໃນປັດຈຸບັນ Next.js 13 ໄດ້ຮອງຮັບການເຮັດ Backend ໄດ້ແລ້ວ ໂດຍທີ່ບໍ່ຈຳເປັນຕ້ອງເພິ່ງແພັກເກດເສີມຕົວອື່ນເລີຍ ໂດຍການໃຊ້ `route.js`
# route.js
ເປັນໜຶ່ງໃນຟາຍພິເສດຂອງ Next.js 13 (loading, error, layout...) ທີ່ມີໜ້າທີ່ເກັບຕົວ Function ທີ່ໄວ້ກັບ Backend API ໂດຍທີ່ບໍ່ຈຳເປັນຕ້ອງເພິ່ງຕົວແພັກເກດເສີມອື່ນໆ.
## 1. ການດຶງຂໍ້ມູນ ຈາກພາຍໃນ Project

```js
export async function GET(request) {

  // Handle GET request for /api/users
  // Retrieve the users from the database or any data source
  const users = [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
    { id: 3, name: 'Joe' },
  ];  
  //Send the users as a response
  return new Response(JSON.stringify(users));

}
```
ນີ້ແມ່ນຕົວຢ່າງໃນການສ້າງ Function ໃນການຈັດການກັບ HTTP Method ໃນການຮ້ອງຂໍຂໍ້ມູນ ດ້ວຍ GET.
### 1.1 ສ້າງຟາຍ JSON ພາຍໃນຕົວໂປຣເຈັກ
![[Pasted image 20230528103942.png]]

```json
[
  {
    "id": "RA101",
    "title": "React Front To Back",
    "description": "Learn Modern React, Including Hooks, Context API, Full Stack MERN & Redux By Building Real Life Projects.",
    "link": "https://www.traversymedia.com/Modern-React-Front-To-Back-Course",
    "level": "Beginner"
  },
  {
    "id": "NJ101",
    "title": "Node.js API Masterclass",
    "description": "Build an extensive RESTful API using Node.js, Express, and MongoDB",
    "link": "https://www.traversymedia.com/node-js-api-masterclass",
    "level": "Intermediate"
  },
  {
    "id": "JS101",
    "title": "Modern JavaScript From The Beginning",
    "description": "37 hour course that teaches you all of the fundamentals of modern JavaScript.",
    "link": "https://www.traversymedia.com/modern-javascript-2-0",
    "level": "All Levels"
  },
  {
    "id": "NX101",
    "title": "Next.js Dev To Deployment",
    "description": "Learn Next.js by building a music event website and a web dev blog as a static website",
    "link": "https://www.traversymedia.com/next-js-dev-to-deployment",
    "level": "Intermediate"
  },
  {
    "id": "PJ50",
    "title": "50 Projects in 50 Days",
    "description": "Sharpen your skills by building 50 quick, unique & fun mini projects.",
    "link": "https://www.traversymedia.com/50-Projects-In-50-Days",
    "level": "Beginner"
  }
]
```
ຈາກນັ້ນ,​ ໃຫ້ເຮັດການສ້າງ route ຂຶ້ນມາເພື່ອເຮັດການດຶງຂໍ້ມູນດັ່ງກ່າວ
```js
import { NextResponse } from "next/server";
import courses from "./data.json";    //Import Data from .json file
import { v4 } from "uuid";

//ສ້າງ GET method ໃນການຕອບຮັບການຮ້ອງຂໍ້
export async function GET(request) {
  return NextResponse.json(courses);
}

//ສ້າງ POST method ໃນການຮັບການເພີ່ມຂໍ້ມູນ
export async function POST(request) {
  const { title, description, level, link } = await request.json();
  const newCourse = {
    id: v4(),
    title,
    description,
    level,
    link,
  };

  courses.push(newCourse);
  return NextResponse.json(courses);
}
```
### 1.2 ການດຶງຂໍ້ມູນ
ຈາກນັ້ນ, ໃຫ້ລອງສົ່ງຄຳຮ້ອງຂໍໄປຫາ API ເຊິ່ງຖ້າຫາກອ້າງອີງຕາມຕຳແໜ່ງຟາຍຂອງ route.js ຈະໄດ້ path ດັ່ງນີ້: `/api/course` (ເອີ້ນໃຊ້ພາຍໃນ Code) ແລະ `http://localhost:300/api/course` ແມ່ນເອີ້ນໃຊ້ໃນເຄື່ອງມືທົດສອບ ໃນຂັ້ນຕອນກຳລັງພັດທະນາໂປເຈັກ
![[Pasted image 20230528110543.png]]

```js
"use client";
import Course from "@/components/Course";
import SearchBar from "@/components/SearchBar";
import { useState, useEffect } from "react";
import Loading from "./loading";

const HomePage = () => {
  const [courses, setCourses] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const fetchCourses = async () => {
      const res = await fetch("/api/course");
      const data = await res.json();
      console.log(data);
      setCourses(data);
      setLoading(false);
    };

    fetchCourses();
  }, []);

  

  if (loading) {
    return <Loading />;
  }

  return (
    <section className="flex flex-col items-center justify-center w-full text-center">
      <h1 className="mb-4 text-2xl font-bold">Welcome To Code Talker</h1>
      <p>The Ultimate Courses from Master of Coding</p>

      <SearchBar
        getSearchResults={(results) => {
          setCourses(results);
        }}
      />
      
      <Course courses={courses} />
    </section>
  );
};

export default HomePage;
```
# 2. ການດຶງຂໍ້ມູນຈາກແຫຼ່ງພາຍນອກ

```jsx
const fetchRepos = async () => {
  const response = await fetch("https://api.github.com/users/jarnket/repos", {
    next: { revalidate: 60 }, //fetch data every 60 seconds
  });

  const data = await response.json();
  
  await new Promise((resolve) => setTimeout(resolve, 1000));

  return data;

};
```
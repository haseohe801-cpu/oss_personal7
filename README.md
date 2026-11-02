선택한 프로젝트_
react-todo-app

선택이유_
수업중 실습을 통해 익힌 내용이라 익숙했고, 처음 react 를 배우는데에 있어 간단한 프로젝트를 분석하고 이해하는 것이 도움이 될 것이라 판단해 이 프로젝트를 선택하였다.

주요 기능 2~3가지_
해야할 일들을 적어서 + 버튼을 눌러 리스트에 저장하는 기능
저장된 일 리스트는 각각 삭제할 수 있는 기능
clear 버튼을 누르면 리스트에 추가된 요소가 전부 삭제되는 기능

Project Structure: 주요 파일 2~3개의 역할_
main.jsx	React 프로그램을 시작하고 App을 화면에 표시
App.jsx	ToDoList 컴포넌트를 불러와 전체 화면을 구성
index.css	배경, 색상, 글꼴, 버튼, Todo 목록 디자인을 담당

React Component: 주요 컴포넌트 1~2개의 역할_
ToDoList.jsx: 할 일 목록을 관리하는 주요 컴포넌트. 할 일 추가, 완료, 삭제 및 저장 기능을 담당함
ToDoForm.jsx: 사용자가 할 일을 입력하고 추가하거나 전체 삭제할 수 있도록 하는 컴포넌트임

Code Analysis: 코드 1개(약 5~15줄)를 선택하여 동작 원리 설명_
const addTodo = (todo) => {
  if (!todo.text || /^\s*$/.test(todo.text)) return;
  localStorage.setItem('localToDos', JSON.stringify([todo, ...todos]));
  const newTodos = [todo, ...todos];
  setTodos(newTodos);
};

addTodo는 새로운 할 일을 추가하는 기능을 담당함
입력 내용이 없거나 공백만 있으면 추가하지 않음
localStorage를 이용해 할 일 목록을 브라우저에 저장함
기존 목록 앞에 새로운 할 일을 추가함
setTodos를 사용해 화면에 변경된 목록을 표시함

Customizing_
1. Text와 UI_
ToDoList.jsx_
<h1>What tasks do you have on your To Do list for today?</h1> ->
<h1>My Daily Planner</h1>
<p className="subtitle">Plan your day, one task at a time!</p>

기존 제목을 My Daily Planner로 변경
새로운 안내 문구를 추가

2. style_background_
index.css_
linear-gradient(90deg, #e03ce0 0%, #8932db 100%); ->
background: linear-gradient(90deg, #dbeafe 0%, #dd0853 100%);

background: #e750a3; -> background: #ffffff;

border: solid #000 10px; -> border: solid #2563eb 3px; border-radius: 15px;

기존 h1 부분에 내용 추가_color: #1e3a8a;
<h1 style={{ color: '#1e3a8a' }}>My Daily Planner</h1>

CSS 아래에 추가_
.subtitle {
  color: #d20404;
  font-size: 14px;
  margin-bottom: 20px;
}

3. UI/data
placeholder="Enter your To Do task here..." ->
placeholder="What do you need to do today?"

실행결과
Text	ToDoList.jsx	제목이 My Daily Planner로 변경됨
Text	ToDoForm.jsx	입력 안내 문구 What do you need to do today? 로 변경됨
Style	index.css	배경과 Todo 박스 색이 변경됨
UI	ToDoList.jsx	안내 문구 디자인이 변경됨



weekly review_
새롭게 배운 내용 3가지_
Component를 기능별로 나누어 웹사이트를 구성하는 방법을 알게 되었다.
useState를 사용하여 할 일 목록을 관리하고 화면을 업데이트하는 방법을 배웠다.
localStorage를 사용하여 새로고침을 눌러도 일 목록이 유지되도록 하는 방법을 배웠다.

어려웠던 점과 해결 방법_
처음 배우는 것이다 보니, React 프로젝트의 구조와 각 파일의 역할을 이해하는 것이 조금 헷갈렸다.
특히 컴포넌트끼리 데이터를 전달하고 연결하는 부분이 헷갈렸다.
각 파일의 코드를 하나씩 확인하고 AI한테 코드를 뜯어 설명해 달라하며 해결했다.

AI 활용 내용 및 느낀 점_
AI를 활용하여 기존 코드의 구조와 각 컴포넌트의 역할을 파악했다.(코드를 주며 쉬운 설명 요구)
수정하는 것은 구조가 이해되면 간단하므로 AI의 도움을 받지 않았다.
AI를 통해 낯선 React 코드를 더 쉽게 이해할 수 있었고, 혼자서 공부하는 것보다 훨씬
빠른 속도로 구조를 이해할 수 있어 좋았다.



<a name="readme-top"></a>
<!-- TABLE OF CONTENTS -->

# 📗 Table of Contents

- [📖 About the Project](#about-project)
  - [🛠 Built With](#built-with)
    - [Tech Stack](#tech-stack)
    - [Key Features](#key-features)
  - [🚀 Live Demo](#live-demo)
- [💻 Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Setup](#setup)
  - [Install](#install)
  - [Run tests](#run-tests)
  - [Usage](#usage)
- [👥 Authors](#authors)
- [🤝 Contributing](#contributing)
- [⭐️ Show your support](#support)
- [🙏 Acknowledgements](#acknowledgements)
- [📝 License](#license)

<!-- PROJECT DESCRIPTION -->

# 📖 To Do Application <a name="about-project"></a>

This is a **simple To Do app** built with React and Vite. It allows users to add, remove, and mark as completed To Do items. The app is fully functional and can be used to manage your daily tasks.

The app is built using React components, which makes it easy to maintain and extend. The code is well-organized and commented, making it easy to understand. The app is also responsive and works well on all screen sizes.

To use the app, simply add a new To Do item by entering the text in the input box and clicking the "Add Todo" button. To remove a To Do item, click the "Remove" button next to the item. To mark a To Do item as completed, click the checkbox next to the item.

The app is open source and available on GitHub. Feel free to fork the project and make your own changes.

## 🛠 Built With <a name="built-with"></a>
* React
* Vite
* JSX
* CSS
* Javascript ES6
* Visual Studio Code
* ESLint
* Stylelint

<!-- Features -->

### Key Features <a name="key-features"></a>

> The key features of this project include the following.

- **It is a simple calculator that can be used to perform basic mathematical operations.**
- **Add, remove, and mark as completed To Do items.**
- **Fully functional and easy to use.**
- **Built with React and Vite.**
- **Well-organized and commented code.**
- **Responsive and works well on all screen sizes.**
- **Open source and available on GitHub.**

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LIVE DEMO -->

## 🚀 Live Demo <a name="live-demo"></a>

- Live Demo of the Project coming soon

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->

## 💻 Getting Started <a name="getting-started"></a>
Get ready to explore the cosmos with these steps:

### Prerequisites <a name="prerequisites"></a>

Ensure you have:
 - A Web Browser such as Microsoft Edge or Google Chrome 🌐
 - Git 🐙
 - A code editor such as Visual Studio Code 👨‍💻

### Setup <a name="setup"></a>

Use `git clone` to get your local copy of the project.

```bash
git clone https://github.com/katarighe/react-todo-app.git
```

### Install <a name="install"></a>

 Run `npm install` to set up the required packages.

```bash
npm install
```

### Run Tests <a name="run-tests"></a>
To run tests run the following command in your terminal
```
 npm test
```

### Usage <a name="usage"></a>

Launch the app with the following command

```
  npm run dev
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- AUTHORS -->

## 👥 Authors <a name="authors"></a>

👤 **Mohamed Aden Ighe**

- GitHub: [@katarighe](https://github.com/katarighe)
- Twitter: [@katarighe](https://twitter.com/katarighe)
- LinkedIn: [@mighe](https://linkedin.com/in/mighe)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONTRIBUTING -->

## 🤝 Contributing <a name="contributing"></a>

Contributions, issues, and feature requests are welcome!

Feel free to check the [issues page](../../issues/).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- SUPPORT -->

## ⭐️ Show your support <a name="support"></a>

Give a star⭐️ or a thumbs up 👍 if you like this project! You can visit my GitHub profile for more of my projects.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ACKNOWLEDGEMENTS -->

## 🙏 Acknowledgments <a name="acknowledgements"></a>

- Project supervised by [Microverse](https//www.microverse.org/)
- [Creative Commons 4.0 License](https://creativecommons.org/licenses/by-nc/4.0/)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- LICENSE -->

## 📝 License <a name="license"></a>

This project is [MIT](./LICENSE) licensed.

<p align="right">(<a href="#readme-top">back to top</a>)</p>
ReactJS로 웹 서비스 만들기
=========================
이 프로젝트는 [Nomad Coders](https://academy.nomadcoders.co/)의 니콜라스님 강의를 토대로 진행했습니다.

## `3일차`
### Promise
- promise는 새로운 Javascript 컨셉이다.
- promise는 asynchronous(비동기식) 프로그래밍이다.
- 비동기식 프로그래밍이 좋은 이유는 다른 작업을 스케쥴해놓을 수 있기 때문이다.
- fetch는 url을 ajax로 심플하게 불러올 수 있다.<br>

### Await, Async
- promise 라인들을 조금 더 분명하게 작성해 주는 도구이다.
- Await와 Async를 쓰는 이유는 애플리케이션이 커지면 then 안에 then으로 이어지면서 call back hell에 빠지기 때문이다.
<pre><code>componentDidMount() {
    this._getMovies();
}</code></pre>
- 아래와 같이 function을 쓰는 이유는,
     1. componentDidMount가 커지지 않도록 하기 위해(사이즈가 크면 좋은 코딩 방법이 아님)
     2. 많은 코드가 한군데에 몰아있는 것 보다는, 작은 function들이 각기 다른 장소에 있는 것이 좋다.

- 



<br><br>
---
This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

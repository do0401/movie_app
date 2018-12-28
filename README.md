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
- 비동기 코드를 작성하는 새로운 방법이다.
- await와 async를 쓰는 이유는 애플리케이션이 커지면 then안에 then으로 이어지면서 call back hell에 빠지기 때문이다.
- 또한 await와 async는 비동기 코드의 겉모습과 동작을 조금 더 동기 코드와 유사하게 만들어준다.
```javascript
componentDidMount() {
    this._getMovies();
}
```
- 위와 같이 function을 쓰는 이유는,
     1. componentDidMount가 커지지 않도록 하기 위해(사이즈가 크면 좋은 코딩 방법이 아님)
     2. 많은 코드가 한군데에 몰아있는 것 보다는, 작은 function들이 각기 다른 장소에 있는 것이 좋다.
```javascript
componentDidMount() {
    this._getMovies();
}

_getMovies = async () => {
    const movies = await this._callApi()
    this.setState({
        movies
    })
}

_callApi = () => {
    return fetch('https://yts.am/api/v2/list_movies.json?sort_by=download_count')
    .then(response => response.json())
    .then(json => json.data.movies)
    .catch(err => console.log(err))
}
```
- 위 코드에서 await로 하는 것은 call api 기능이 '끝나는 것'을 기다리고, return value를 movies에 넣는다.
- 그리고 setState를 movies로 한다. 단, setState는 call api 작업이 완료되기 전 까지는 실행되지 않는다.
- 컴포넌트의 key는 index를 사용하면 느리기 때문에 사용하지 않는 것이 좋다.

> async와 await 참고 페이지 : [자바스크립트의 Async/Await 가 Promises를 사라지게 만들 수 있는 6가지 이유](https://medium.com/@constell99/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EC%9D%98-async-await-%EA%B0%80-promises%EB%A5%BC-%EC%82%AC%EB%9D%BC%EC%A7%80%EA%B2%8C-%EB%A7%8C%EB%93%A4-%EC%88%98-%EC%9E%88%EB%8A%94-6%EA%B0%80%EC%A7%80-%EC%9D%B4%EC%9C%A0-c5fe0add656c)
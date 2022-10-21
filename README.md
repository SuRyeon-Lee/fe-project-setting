# ⚒️ FE 프로젝트 세팅 해보기
프로젝트를 처음 시작할 때 fe의 입장에서 세팅해야 할 것들을 실습해보았습니다.

</br></br>

## 🔥 Create React App
```bash
npx create-react-app {원하는 디렉터리 경로}
```

</br></br>

## 🔥 Redux
리덕스 공식문서 [Quick Start](https://redux.js.org/tutorials/quick-start) 참고해서 리덕스 설치
```bash
npm install @reduxjs/toolkit react-redux
```

</br></br>

## 🔥 Styled Component
Styled Component의 [Getting Started](https://styled-components.com/docs/basics#installation)를 참고하여 Styled Component를 설치
```bash
npm install --save styled-components
```

</br></br>

## 🔥 ESlint, Prettier
```bash
npm install -D eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-prettier eslint-config-prettier
```
* Prettier는 **formatter**고 eslint는 **linter**이다. 두 개의 차이점과 사용법을 알아야 더 스마트하게 사용할 수 있다.
* 오류를 잡으려면 린터, 스타일을 교정하려면 포맷터를 사용한다.
* prettier와 eslint를 같이 사용하려면 설정이 필요하다. [링크참조](https://yrnana.dev/post/2021-03-21-prettier-eslint)

|패키지명|역할|
|:---:|:---:|
|eslint-plugin-import|ES6+ import/export 문법의 린팅을 지원하고, 파일 경로와 import 이름의 오타를 예방. 이러한 것들을 마크업 에디터에 표시해주는 모듈.|
|eslint-plugin-jsx-a11y|JSX 내의 접근성 문제에 대해 즉각적인 AST 린팅 피드백을 제공. 많은 IDE가 코드 분석과 소스 코드 창에 이런 결과를 통합할 수 있도록 해줌.[링크](https://ko.reactjs.org/docs/accessibility.html#eslint-plugin-jsx-a11y)|
|eslint-plugin-react|리액트와 관련된 룰을 정의한 패키지. 리액트에서 eslint 쓸때 필요|
|eslint-plugin-react-hooks|리액트 훅과 관련된 룰을 강제하는 패키지. 리액훅 안전하게 쓰려면 필요[링크](https://reactjs.org/docs/hooks-rules.html#eslint-plugin)|
|eslint-plugin-prettier|eslint에서 prettier와 충돌할 수 있는 rule을 꺼버림 ✅ 코드 오류를 잡는데는 eslint, 코드 포맷팅에는 prettier를 사용하는 방법이다.|
|eslint-config-prettier|prettier를 eslint의 rules로 동작하게 함.포맷팅 문제도 오류로 출력되어서 오류 메시지가 지나치게 많아지며 느리다.=>[권장하지 않는 글도 있음](https://yrnana.dev/post/2021-03-21-prettier-eslint)|

</br>

* ⬇️.eslint.json 파일설정
```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:import/recommended",
    "plugin:jsx-a11y/recommended",
    "plugin:prettier/recommended"
  ],
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "rules": {
    "react/react-in-jsx-scope": 0,
    "react/jsx-uses-react": 0
  }
}
```
* ⬇️.prettierrc.json 파일설정
```json
{
  "singleQuote": true
}
```

*  [cmd +,] 를 눌러서 VScode setting 으로 들어가서 `editor.codeActionsOnSave`설정을 아래와 같이 조정하면, 저장할 때 마다 ESlint가 고칠 수 있는 에러와 코드 스타일링을 자동으로 고쳐주기 때문에 편리하게 개발할 수 있다.
```json
{
    "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
    }
}
```

</br></br>

## 🔥 License 추가하기
* [깃허브 라이센스 추가하기](https://jaeryo2357.tistory.com/8)글 등을 참고하여 리모트에서 깃허브에서 제공하는 라이센스를 간편하게 추가한 뒤 `git pull --rebase origin main`으로 로컬로 땡겨오기

</br></br>

## 🔥 Github Project 칸반을 만들고, 이슈와 마일스톤을 연결하기
깃허브 페이지에서 테스크를 보기 쉽게 정리한다.

</br></br>

## 🔥 Git flow에따라 브랜치 분기하기
Git flow를 단순화한 Coz’ Git flow로 실습해본다.
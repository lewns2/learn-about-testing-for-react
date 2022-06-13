# 타이머 앱 테스트

## 1. 프로젝트 생성
```
yarn add create react-app timer-test-app
```

**yarn을 선택한 이유**
npx(npm)과 yarn 중 yarn을 통해 프로젝트를 사용하는 이유는 `npm audix fix`로 해결되 지않는 취약점때문에 어쩔 수 없이 yarn을 선택했습니다. 

> (나중에 npm과 yarn 비교해보기)
> [node_modules로부터 우리를 구원해 줄 Yarn Berry](https://toss.tech/article/node-modules-and-yarn-berry)  

## 2. ESLint 설정하기
1. `.eslintrc.json` 파일 생성하기
2. testing을 위한 eslint 플러그인 설치
> ESLint Plugin 이란? <br>
> eslint에서 기본으로 제공하지 않는 다양한 규칙을 플러그인을 통해 사용

### Eslint Testing Plugins 설치
테스트 시, render로 DOM을 그리는 역할을 하는 `testing-library`와 expect-matcher로 테스팅 부분을 위해 `jest-dom` 설치

**install eslint-plugin-testing-library**
```
yarn add --dev eslint-plugin-testing-library
```

**install eslint-plugin-jest-dom**
```
yarn add --dev eslint-plugin-jest-dom
```

3. 설치한 플러그인을 eslint 설정

**.eslintrc.json**
```json
{   
    /* 외부 플러그인 추가 */
    "plugins": [
        "testing-library",
        "jest-dom"
    ],

    /* 실 사용을 위한 규칙 설정 */
    "extends": [
        "react-app",
        "react-app/jest",
        "plugin:testing-library/react",
        "plugin:jest-dom/recommended"
    ]
}
```

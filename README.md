# Webpack-template-basic

## Package Install

```bash
npm i -D webpack webpack-cli webpack-dev-server@next
```

package.json
```
"scripts": {
    "dev": "webpack-dev-server --mode development",
    "build": "webpack --mode production"
  },
```
- dev : 현재 개발 모드
- build : 제품 모드
- webpack : bundler가 동작하기 위한 핵심 package
- webpack-cli : Command Line Interface 지원
  - parcel은 자동 지원
- webpack-dev-server : dev를 통해 server를 open 할 때 바로 새로고침하기 위해서 사용

## webpack.config.js

webpack은 브라우저에서 동작하는 것이 아닌 Node.js 환경에서 동작한다.

## npm run build

> 개발 서버 오픈 : npm run dev
> 제품화 : npm run build

컴파일 + 링크 : 분석한 소스코드로 실행 가능한 프로그램을 만듦</br>
package.json에서 build 스크립트 부분이 실행되고, 여기에 webpack이 있다면 실행되는 원리

## 개발 서버 오픈

```bash
npm i -D html-webpack-plugin
```

webpack.config.js -> plugins 추가 -> ```npm run dev```

## Favicon 설정(정적 파일 연결)

```npm i -D copy-webpack-plugin```

## module(CSS파일 읽게 하기)

```npm i -D css-loader style-loader```

## SCSS

```npm i -D sass-loader sass```

## Autoprefixer

```npm i -D postcss autoprefixer postcss-loader --legacy-peer-deps```

- packag.json
  ```
  "browserslist": [
     "> 1%",
     "last 2 versions"
  ]
  ```

- .postcssrc.js 파일 생성

## babel

```npm i -D @babel/core @babel/preset-env @babel/plugin-transform-runtime```

- .babelrc.js 파일 생성

- webpack.config.js
  ```
  {
        test: /\.js$/,
        use: [
          'babel-loader'
        ]
      }
  ```

  ```npm i -D babel-loader```

## Netify 배포

Login - New site from Git - Github - webpack-template-basic 선택

> 개발 서버 오픈 : npm run dev</br>
> 제품화 : npm run build

- Build command = npm run build
- Publish directory = dist/ (변경 시 수정할 것)

Deploy site - 주소 접근

## NPX, Degit

새로운 Terminal Open

- 경로 확인
  ```bash
  ls
  ```
- 다운 받기 원하는 경로로 이동
  ```bash
  cd [원하는 경로]
  ```
- 설치
  ```bash
  npx degit [Github 이름]/[다운 받을 폴더 이름] [다운 시 원하는 폴더 이름]
  ```

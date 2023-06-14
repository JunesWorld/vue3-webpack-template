# Vue3-webpack-template

## Package Install

```bash
npm i vue@next
npm i -D vue-loader@next vue-style-loader @vue/compiler-sfc
npm i -D file-loader
```

## webpack.config.js 수정

module/rules
- vue라는 확장자를 가지고 있는 파일을 필터링해서 vue-loader가 실행될 수 있게 설정
- file을 읽을 수 있는 file-loader

test
- style부분이 해석 될 수 있게 vue-style-loader 추가

전역 모듈
- VueLoader에서 Plugin을 가져와 해당 내용을 plugins에서 생성자 함수를 실행하도록 설정

module.exports/resolve
- 경로 명시 시 확장자 생략할 수 있게 함
- alias: 경로별칭 사용하면 해당 경로로 바로 jump
  ```Javascript
  // alias=경로별칭
    // ~ 사용하면 해당 경로로 바로 jump
    alias: {
      '~': path.resolve(__dirname, 'src'), // 폴더가 모여 있는 경로
      'assets': path.resolve(__dirname, 'src/assets') // 실제 이미지가 있는 경로
    }
  },
  ```

## 시작하기

```HTML
<body>
  <div id="app"></div>
</body>
```

```Javascript
// CDN
// import Vue from 'vue'

// CLI
// Vue 객체가 없다
import { createApp } from 'vue'
import App from './App.vue'

// HTML에서 app이라는 값을 가지고 있는 해당 요소에 vue 프로젝트 연결
// 1. CDN
//Vue.createApp(App).mount('#app')

// 2. CLI
createApp(App).mount('#app')
```

```bash
npm run dev
```
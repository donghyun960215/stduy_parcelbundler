# parcel bundler

## parcel bundler 시작하기
```plaintext
1. npm init -y 를 통해서 package.json 다운로드(npm 프로젝트 시작)
2. npm i -D parcel-bundler 를 통해서 개발 의존성 패키지로 parcelbundler 다운로드(node_modules 폴더와 package-look.json 설치가 됐는지 확인)
3. package.json 안에 script 부분 수정
    "dev":"parcel index.html",
    "build":"parcel build index.html"
    추가
4. js 파일과 scss(css) 파일 생성
5. <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css"> resct.css CDN 으로 css 리셋해주기
6. npm run dev 입력해서 시작!
```

## favicon.ico (정적파일 연결)
```plaintext
favicon.ico (웹페이지 아이콘) 사용시 (https://www.icoconverter.com/ 여기서 일반 이미지를 favicon.ico로 변환가능)
1. npm i -D parcel-plugin-static-files-copy 를 입력해서 개발 의존성으로 다운로드
2. package.json 에 속성 추가
    "staticFiles": {
    "staticPath": "static"
  }
3. 새로운 폴더 static 만들고 정적파일
```

## autoprefixer
```plaintext
1. npm i -D postcss 를 입력해서 개발 의존성으로 다운로드
2. npm i -D autoprefixer 를 입력해서 개발 의존성으로 다운로드
3. package.json 에서 새로은 옵션 추가
    "browserslist": [
    "> 1%",
    "last 2 versions"
  ]
4. .postcssrc.js 이름으로 새로운 파일 추가
    nodejs 방식으로 import와 export 를 해준다.
```
```plaintext
*javascript 방식의 import 와 export 
import autoprefixer from 'autoprefixer'

    export{
        Plugins: [
            autoprefixer
        ]
} 

*nodejs 방식의 import와 export
const autoprefixer = require('autoprefixer')

module.exports = {
    Plugins: [
        autoprefixer
    ]
}
간소화
module.exports = {
    Plugins: [
        require('autoprefixer')
    ]
}
```
```plaintext
5. 그 후 npm run dev 로 실행을 하게 되면 postcss 와 autoprefixer 의 버전 충돌이 일어난다.
6. autoprefixer 를 다운그레이드를 해준다.(npm i -D autoprefixer@9 를 입력해서 9버전으로 다운로드)
7. 그 다음 실행을 하게 되면 정상 작동을 한다.
8. css로 display: flex;를 입력하고 브라우저에서 개발자모드로 그 부분을 눌러서 보게 되면 
   내가 작성한 display빼고도 구형버전에 맞게 새로 추가가 되면서 밑줄이 그어져 있다.
```

## babel
```plaintext
Babel은 ECMAScript 2015+(ES6) 코드를 이전 JavaScript 엔진에서 실행할 수 있는 이전 버전과 호환되는 JavaScript 코드로 변환하는 데 
주로 사용되는 무료 오픈 소스 JavaScript 트랜스컴파일러입니다. 웹 개발자는 언어의 최신 기능을 활용할 수 있습니다.
구형 버전의 브라우저에서도 작동을 할 수 있게 해주는 프로그램이다.

ES6

ES7           --------------------->             ES5
                        BABEL
ES8
```
```plaintext
1. npm i -D @babel/core @bable/preset-env
   npm i -D @babel/plugin-transform-runtime
   npm i -D @bable/preset-env
   를 입력하여 개발의존성 모드로 다운로드
2. .babelrc.js 파일 생성 후 nodejs 방식으로 import와 export 해준다.
    module.exports = {
    preset: ['babel/preset-env'],
    plugin: [
        ['@babel/plugin-transform-runtime']
    ]
  }
3. package.json 에 옵션 추가
    내용은 postcss를 추가할 때 사용했던 옵션과 동일하다 
    babel 추가시 이미 postcss를 추가해서 package.json 에 옵션을 추가 했다면 안해도 된다.
```


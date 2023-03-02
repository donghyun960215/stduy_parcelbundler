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
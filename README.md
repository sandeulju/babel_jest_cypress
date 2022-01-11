## Frontend - Preset

- [x] npm init

  - 명령어
    - npm init
    - npm init -y

- [x] gitignore

  - extension -> gitignore 검색 (가장 조회수 많은 거 다운)
  - ctrl + shift + p -> add gitignore 검색
  - node 검색 -> 실행

- [x] nodemon
  - npm i -D nodemon
  - ```json
      "scripts": {
            "start": "nodemon ./index.js",
            },
    ```
    
  - npm (run) start

- [x] Babel
   - npm i -D @babel/core @babel/preset-env @babel/cli @babel/node
      - 만약 오류 발생시 npm -g i -D @babel/core @babel/preset-env @babel/cli @babel/node
   - 루트 디렉토리에 **babel.config.json** 파일 생성
      - ```json
          {
             "presets": ["@babel/preset-env"]
          }
          ```
     - ```json
         "scripts":{
              "start": "nodemon --exec babel -node ./index.js",
         },
         ```
         
     - npm (run) start

- [x] Eslint & Prettier

    - npm install eslint --save-dev
    - npx eslint --init
    - init 설정
    - npm i -D eslint-config-prettier eslint-config-tui
    eslint-plugin-prettier prettier
    - ```json
        "lint": "eslint ./index.js --fix"
      ```
    - eslintc.js
-  ```javascript
    module.exports = {
    parserOptions: {
        sourceType: "module"
    },
    env: {
        browser: true,
        es6:true
    },
    extends: ['eslint-config-tui', 'prettier'], 
    plugins: ["prettier"],
    rules: {
        "prettier/prettier": "error",
    },
};
      
- [x] Jest

    - npm install --save-dev jest babel-jest
    - jest.config.json 파일 생성
    - ```json
        {
            "clearMocks": true,
            "collectCoverage": true,
            "verbose": true,
            "testEnvironment": "jsdom"
        }
    - script 수정
    - ```json
        "scripts": {
            "test:jest": "jest --watchAll --collect[=true] --logHeapUsage"
            }
    - test 폴더 하위에 (원하는 파일명).test.js 파일 생성
   

**주의사항!!**
  ```javascript
      // export랑 함수 || 객체가 한계일 경우
      const sum = (a + b) => {
          return a + b;
      };
      
      export default sum;
      // 테스트 파일
      import sum from "../src/index.js";
      //테스트 컨텍스트
  ```
      
  ```javascript
      // export랑 함수 || 객체가 다수일 경우
      export const sum = (a, b) => {
          return a + b;
        };
        
      export const minus = (a, b) => {
          return a - b;
        };
        //테스트 파일
        
      import { sum, minus } form "../src/index.js";
      //테스트 컨텍스트
  ```
      
  
  
- [x] parcel
 
    - npm install --save-dev parcel
    - npx parcel src/index.html (만약 src 폴더 하위에 index.html 파일이 있다면)
    - ```json
        "scripts": {
            "start": "parcel",
            "build": "parcel build"
            },

        
- [ ] Cypress

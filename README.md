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

- [x] Eslint

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
```
      
- [ ] Prettier
- [ ] Jest
- [ ] Cypress

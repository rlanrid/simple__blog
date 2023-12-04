## client
npx create-react-app .   
npm install react-bootstrap bootstrap   
npm install react-router-dom   
npm install axios
npm install http-proxy-middleware
npm install @emotion/css
npm install @emotion/react
npm install @emotion/styled

## server
npm init;   
npm init -y;   
npm install express --save;   
npm install nodemon --save;
npm install path --save;
npm install mongoose --save;

## 제작과정
```js
const express = require("express");
const app = express();
const port = 5050;

app.listen(port, () => {
    console.log("running --> " + port);
});

app.get("/", (req, res) => {
    res.send("Hello World");
});
```

- express 설치 과정


```js
app.use(express.static(path.join(__dirname, "../client/build")));
```

- Express 애플리케이션에서 정적 파일을 제공하기 위한 middleware를 설정하는 부분



## mongoose 셋팅
```js
const mongoose = require("mongoose");

app.listen(port, () => {
    mongoose.connect(
        'mongodb+srv://rladnrider77:forever0@cluster0.vckv8nq.mongodb.net/reactBlog?retryWrites=true&w=majority'
    ).then(() => {
        console.log("listening --> " + port);
        console.log("mongoose connecting...");
    }).catch((err) => {
        console.log(err);
    })
})
```


## body 파싱
```js 
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
```
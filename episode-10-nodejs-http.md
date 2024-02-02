## Using NodeJS ( fs,http)

- အရင်ဆုံး မိမိ project မှာ node js ကို သုံးနိုင်ဖို့ node ကို init လုပ်ပေးရပါမယ်
- terminal မှာ မိမိ project ရှိတဲ့နေရာ ကို အရင်၀င်ပါ.
- ပြီးရင်အောက်က command ထည့်ပြီး enter ခေါက်ပါ

```console
npm init -y
```

- npm ကို သုံးပြီး node js ကို initialize လုပ်လိုက်တာဖြစ်ပါတယ်
- `-y` ကတော့ init လုပ်တဲ့အချိန် ထည့်ပေးရမယ့် info တွေကို default အတိုင်းပဲ ထားခိုင်းလိုက်တာဖြစ်ပါတယ်
- init လုပ်ပြီးတဲ့အချိန် package.json ဆိုပြီး fileတစ်ခု project folder ထဲ ရောက်လာမှာဖြစ်ပါတယ်

```js
{
  "name": "nodejs-test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",

}
```

##

### fs ( file system ) module

- nodejs မှာ build in ပါလာပြီးသား module တွေထဲက file တွေကို စီမံခန့်ခွဲနိုင်တဲ့ fs module ကို လေ့လာကြမှာဖြစ်ပါတယ်
- nodejs မှာ အခြား developer တွေ ဖန်တီးထားတဲ့ package တွေကို npm နဲ့ install လုပ်ပြီး အသုံးပြုလို့ရပါတယ်
- nodejs မှာ ထည့်သွင်း/အသုံးပြုလို့ရတဲ့ package တွေကို node module လို့လဲခေါ်ပါတယ်
- fs ကို လေ့လာတဲ့အခါမှာ typescript နဲ့ ရေးမှာမလို့ typescript ကို compile လုပ်စရာမလိုပဲ တစ်ခါတည်း run ပေးနိုင်တဲ့ ts-node-dev ဆိုတဲ့ module ကို install လုပ်ပြီး အသုံးပြုပါမယ်။

```console
npm i ts-node-dev
```

- install ပြီးတာနဲ့ project folder ထဲမှာ node_module folder နဲ့ package-lock.json ဆိုပြီး file တစ်ခု တိုးလာမှာဖြစ်ပါတယ်
- ဒါ့အပြင် package.json ထဲမှာလည်း `dependencies` ဆိုတဲ့ object တစ်ခုတိုးလာပြီး ခုနက ထည့်ထားတဲ့ ts-node-dev ကို ပြပေးနေမှာဖြစ်ပါတယ်
- node_modules folder မှာတော့ Dependencies မှာရှိတဲ့ module တွေရဲ့ data တွေကို သိမ်းထားပေးပြီး ဖိုင်တွေ အများကြီး ရှိတက်ပါတယ်
- package-lock.json ကတော့ Dependencies တွေ ချိတ်ဆက်ထားတဲ့ ဖိုင်ဖြစ်ပါတယ်
- node_module folder နဲ့ package-lock.json တွေကို ပြင်ဆင်ခြင်းမပြုလုပ်ပဲ ဒီအတိုင်းပဲ ထားပေးရပါမယ်

##

### Run NodeJS server

- node js server ကို run နိုင်ဖို့ နည်းလမ်းနှစ်မျိုးကို သုံးလို့ရပါတယ်

### node file-name.file-extension

- terminal မှာ `node script.ts` လို့ မိမိrun ချင်တဲ့ ဖိုင်ကို node server နဲ့ တစ်ခါတည်း run နိုင်ပါတယ်

### using script

- နောက်တစ်နည်းကတော့ package.json file ထဲမှာ script တစ်ခု လုပ်ပြီး command နဲ့ run ခိုင်းတာဖြစ်ပါတယ်။

```json
{
  "name": "nodejs-test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "ts-node-dev script.ts"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "ts-node-dev": "^2.0.0"
  }
}
```

- script object အောက်မှာ `"start": "ts-node-dev script.ts"` ဆိုတဲ့ script တစ်ခု ထည့်ပြီး ts-node-dev နဲ့ run ချင်တဲ့ ဖိုင်နာမည် ထည့်ပေးလိုက်တာဖြစ်ပါတယ်
- node server ကို run ချင်ရင် တော့ **_`npm start`_** ဆိုပြီး terminal မှာ ရိုက်ထည့်ပေးရမှာဖြစ်ပါတယ်
- node server ကို stop ( kill ) ချင်ရင်တော့ `Ctrl` + `c` ကို တွဲနှိပ်ပေးရမှာဖြစ်ပါတယ်

##

### http and server

#### http ဆိုတာ _server( backend)_ နဲ့ _browser(frontend)_ ကို ချိတ်ဆက်ပေးတဲ့ နည်းပညာ ဖြစ်ပါတယ်။ node js မှာ http ကို အသုံးပြုပြီး web server တစ်ခုကို ကိုယ်တိုင် တည်ဆောက်လို့ရပါတယ်။

#### server ဆိုတာက browser(frontend) မှာ ပြပေးမယ့် (ပြုလုပ်ချင်တဲ့)အချက်အလက်တွေကို စီမံခန့်ခွဲပေးတဲ့ နေရာ လို့ အလွယ်သတ်မှတ်နိုင်ပါတယ်။

ဆာဗာ ကို ၀င်ရောက် အသုံးပြုနိုင်ဖို့အတွက်

- **လိပ်စာ( `IP address`)**
- **၀င်ပေါက် ( `port`)** လိုအပ်ပါတယ်။

  > http `IP-address` `:` `port`

      http://127.0.0.1:3000 or http://localhost:3000

### serverကို ထို လိပ်စာနဲ့ ၀င်ပေါက်မှာ အသင့်စောင့်(`listen`) နေပြီး ၀င်လာသမျှ အချက်အလက် ( `request`) တွေကို လက်ခံကာ သက်ဆိုင်ရာ အချက်အလက်များကို ပြန်လည်( `response`) ထုတ်ပေးပါတယ်။

![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/server1.jpg?raw=true)

##

### Setup web-server ( http server )

- server.ts ဖိုင်တစ်ခု လုပ်ပါမယ်

```js
import  http  from  "http";
import  fs  from  "fs";

const  PORT  =  5000;

//create server
const server = http.createServer((request, response) => {
    //// your code here
}

server.listen(PORT, () =>  console.log(" Server Running at PORT -", PORT));
```

> ရှင်းလင်းချက်

```js
import http from "http";
import fs from "fs";
```

- fs module နဲ့ http module ကို import လုပ်ထားပါတယ်

```js
const PORT = 5000;
```

- server အတွက် port တစ်ခု သတ်မှတ်ထားလိုက်ပါတယ်

```js
const server = http.createServer((request, response) => {
     //// your code here
}
```

- http module က createServer method ကို သုံးပြီး http web serverတစ်ခု create လုပ်လိုက်ပါတယ်
- createServer method က callback function တစ်ခုကို လက်ခံပြီး
- အဲ့ဒီ function မှာတော့ **`request`** ( client ကနေ ၀င်လာတဲ့ request ) နဲ့ **`response`** ( server ကနေ ပြန်ထုတ်ပေးတဲ့ response ) ဆိုတဲ့ **parameter နှစ်ခုကို လက်ခံ**မှာဖြစ်ပါတယ်

```js
server.listen(PORT, () => console.log(" Server Running at PORT -", PORT));
```

- server ကို port 5000 မှာ listen လုပ်ထားပေးရမှာ ဖြစ်ပါတယ်
- listen method ရဲ့ callback function ထဲမှာတော့ server run နေကြောင်း log တစ်ခု ထုတ်ပေးထားလိုက်တာပါ
- ခု http server ကို run ဖို့ အတွက် `package.json` file မှာ script ကို သွားပြင်ပေးရပါမယ်

```js
// package.json

{
  "name": "nodejs-test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "ts-node-dev server.ts"//update to server.ts
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "ts-node-dev": "^2.0.0"
  }
}

```

- ခု server ကို npm start နဲ့ run ကြည့်ပါက terminal မှာ အောက်ကပုံလို ပြပေးမှာဖြစ်ပါတယ်

##

### http request method

- http request တွေမှာ အသုံးများတဲ့ METHOD တွေ ကတော့
  - POST
  - PUT
  - GET
  - DELETE
- ဖြစ်ကြပါတယ်

### method တွေကို စာလုံးအကြီးတွေနဲ့ အထက်ပါအတိုင်း ရေးပေးရမှာဖြစ်ပါတယ်

- POST က data တွေ *C*reate လုပ်တဲ့အခါ သုံးလေ့ရှိပါတယ်
- PUT က data တွေ *U*pdate လုပ်တဲ့အခါ သုံးလေ့ရှိပါတယ်
- GET က data တွေ *R*ead လုပ်တဲ့အခါ သုံးလေ့ရှိပါတယ်
- DELETE က data တွေ *D*elete လုပ်တဲ့အခါ သုံးလေ့ရှိပါတယ်

##

### Test http request and response

- node js မှာ http server ကနေ frontend က request တွေကို လက်ခံပြီး response ပြန်လုပ်တာ စမ်းကြည့်ရအောင်

```js
//server.ts

import  http  from  "http";
import  fs  from  "fs";

const  PORT  =  5000;

//create server
const server = http.createServer((request, response) => {
    const method = request.method
    console.log(method)
    response.write(method)
    response.end()
}

server.listen(PORT, () =>  console.log(" Server Running at PORT -", PORT));
```

- Browser ကနေ http://localhost:5000 ကို ၀င်ကြည့်ပါက response ပြန်လာတဲ့ method ကို တွေ့ရမှာဖြစ်ပါတယ်

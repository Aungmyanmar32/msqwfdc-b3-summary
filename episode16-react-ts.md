### what is react?

### React

- React ဆိုတာ UI တွေ ထည်ဆောက်တဲ့နေရာမှာ သုံးတဲ့ JavaScript library တစ်ခုဖြစ်ပါတယ်
- Declarative အနေနဲ့ အသုံးပြုလို့ရပါတယ်
- React က **component base** JavaScript library လည်း ဖြစ်ပါတယ်
- component မှာ class component နှင့် functional component ဆိုပြီး နှစ်မျိုးရှိပါတယ်
- functional component က stable ဖြစ်တဲ့အတွက် functional componentကိုပဲ အသုံးပြုပါမယ်
- React ထဲမှာ html ကော js ပါ တစ်ခါတည်း တွဲရေးလို့ပါတယ်။ **jsx** လို့ ခေါ်ကြပါတယ်။
- jsx element တွေ ရေးတဲ့အခါ ့html element တွေလိုမျိုး အဖွင့်အပိတ် tag တွေနဲ့ ရေးပေးရပါတယ်
- ထူခြားချက်အနေနဲ့ jsx element တွေမှာ self-closing လဲ သုံးလို့ရတာဖြစ်ပါတယ်
- ခု သင်ခန်းစာမှာ TS နဲ့ ရေးမှာမလို့ `.tsx` လို့ သုံးပြီးရေးမှာဖြစ်ပါတယ်
- React က page တစ်ခုထဲမှာပဲ ပြချင်အရာတွေကို render လုပ်ပေးတာမလို့ **SPA (single page application)** လို့လဲ သတ်မှတ်ကြပါတယ်။

### Installation

- react app project တစ်ခု စတင်ဖို့ react ကို Install လုပ်ပေးရပါမယ်

  ```console
    $ npx create-react-app my-app --template typescript
  ```

  - အထက်ပါ command ကို terminal ထဲမှာ ကူးထည့်ပြီး run ပေးပါ
  - `$` ကို ကူးယူရန်မလိုပါ
  - my-app နေရာမှာ မိမိရဲ့ project name ကို ထည့်ပေးပါ(eg - my-class-react)

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146496880365277194/image.png)

- install လုပ်လို့ပြီးရင် ခုလိုပြပေးမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146497531933638696/image.png)

- အခု ခုနက လုပ်ထားတဲ့ react project ကို vs code မှာ ဖွင့်ပေးလိုက်ပါ

```console
$ npm start
```

- browser က auto ပွင့်လာမှာဖြစ်ပြီး ခုလိုပြပေးနေရင် react app က run နေပြီးဖြစ်ပါတယ်။

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146498837008093274/image.png)

##

### File structure

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146499429810049044/image.png)

- public folder ထဲမှာတော့ အဓိကအားဖြင့် index.html ကို လေ့လာကြည့်ရအောင်

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="utf-8" />
      <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <meta name="theme-color" content="#000000" />
      <meta
        name="description"
        content="Web site created using create-react-app"
      />
      <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
      <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
      <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
      <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.
  
      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
      <title>React App</title>
    </head>
    <body>
      <noscript>You need to enable JavaScript to run this app.</noscript>
      <div id="root"></div>
      <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.
  
      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.
  
      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    --></body>
  </html>
  ```

- comment တွေ အများကြီး ရေးပေးထားလို့ ရှုပ်ထွေးနေပေမယ့် ေသချာကြည့်လိုက်ရင် id "root" ပေးထားတဲ့ div တစ်ခုပဲ လုပ်ထားတာကို မြင်ရမှာဖြစ်ပါတယ်

##

### src folder

- src folder ကတော့ project မှာ အဓီက ကိုင်တွယ်သွားမယ့် folder ဖြစ်ပါတယ်
- index.tsx က ခုနက html ဖိုင်ထဲက root div ကို ချိတ်ဆက်ပြီး react code တွေကို UI မှာ ပြပေးနိုင်အောင် (render) လုပ်ပေးမှာဖြစ်ပါတယ်

```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(
  document.getElementById('root') as HTMLElement
);
root.render(
    <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```

- root.render ထဲက <App /> ဆိုတာက src folder အောက်မှာ ရှိတဲ့ App.tsx ထဲမှာ export လုပ်ထားတဲ့ App component ကို import လုပ်ပြီး render လုပ်ထားတာဖြစ်ပါတယ်
- ဆိုလိုတာက App component ထဲမှာ ရေးပြီး return လုပ်ထားတဲ့ data တွေကို ဒီ index.tsx ထဲမှာ ယူပြီး ပြပါမယ် လို ပြောလို့ရပါတယ်

  ### App.tsx

  - ဒီ ဖိုင်ကတော့ react app ထဲက main လို့ပြောလို့ရမယ့် component ဖြစ်ပြီး render လုပ်ချင်တဲ့ တဲ့ data တွေ အကုန်လုံး ဒီထဲကနေပဲ export import လုပ်ကာ အသုံးပြုရမှာ ဖြစ်ပါတယ်
  - ခု အဲ့ဒီဖိုင်ထဲမှာရှိနေတဲ့ code တွေ ဖျက်ပြီး ကျနော်တို့ ကိုယ်ပိုင် component တစ်ခု တည်ဆောက်ကြည့်ပါမယ်

### react component

- react ဟာ component-based ဖြစ်တယ်ဆိုတာ အထက်မှာ ပြောခဲ့ပါတယ်။
- ဒီသင်ခန်းစာမှာတော့ functional component ကို အသုံးပြုပါမယ်။
- react component ဆိုတာ react app မှာ ပါ၀င်တဲ့ **လုပ်ဆောင်ချက်တွေကို တစ်ခုချင်းစီ သက်သက် လုပ်ထား**ပြီး လိုအပ်တဲ့အခါမှ ခေါ်ယူအသုံးပြုနိုင်အောင် ဖန်တီးထားတဲ့ **အစိတ်အပိုင်းတစ်ခု** လို့ အကြမ်းဖျင်း မှတ်ယူနိုင်ပါတယ်။

```js
// App.tsx
import React from "react";

const App = () => {
  const name = "AUNG";
  return <div>{name}</div>;
};

export default App;
```

- react component တွေရဲ့ နာမည်အစကို စာလုံးကြီး နဲ့ ပေးရမှာဖြစ်ပါတယ်
- အဲ့ဒီ component မှာ jsx element တစ်ခုပဲ return လုပ်လို့ရမှာဖြစ်ပါတယ်
- return လုပ်တဲ့အထဲမှာ javascript expression (variable,object,array,function , etc...)တွေ သုံးချင်ရင် `{ }` ထဲထည့်ပြီး သုံးပေးရမှာဖြစ်ပါတယ်
- element တစ်ခုထပ်ပိုပြီး return လုပ်ချင်ရင်တော့ return လုပ်ချင်တဲ့ element တွေကို parent element တစ်ခုနဲ့ wrap လုပ်ပေးရမှာဖြစ်ပါတယ်

```js
// App.tsx

import React from "react";

const App = () => {
  const name = "AUNG";
  return (
    <div>
      <div>{name}</div>
      <h1>Hello World</h1>
    </div>
  );
};

export default App;
```

- ခု react app (browser) မှာ သွားကြည့်ပါက ခုလိုပြပေးမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146508966025760878/image.png)

## create components and using

- ဆက်ပြီး components တွေ တည်ဆောက်ပြီး App.tsx ထဲမှာ ခေါ်သုံးကြည့်တာကို လေ့လာကြည့်ရအောင်
- အရင်ဆုံး src folder အောက်မှာ components folder တစ်ခု လုပ်လိုက်ပါ
- components folder ထဲမှာမှ ကျနော်တို့ အသုံးပြုမယ့် components တွေကို ထည့်ထားမှာဖြစ်ပါတယ်
- components folderထဲမှာ Menu component တစ်ခု တည်ဆောက်ပါမယ်
  ![](https://cdn.discordapp.com/attachments/1146496852087287898/1146662784050921554/image.png)

- Menu component ဆိုတဲ့ h1 တစ်ခုကိုပဲ return လုပ်ထားပါတယ်
- အဲ့ဒီ Menu component ကို App component မှာ import လုပ်ပြီး သုံးကြည့်ပါမယ်

```js
// App.tsx

import React from "react";
import Menu from "./components/Menu";

const App = () => {
  const name = "Aung";
  return (
    <div>
      <div>{name}</div>
      <h1>Hello World</h1>
      <Menu />
    </div>
  );
};

export default App;
```

- Menu component ကို import လုပ်ပြီး return လုပ်တဲ့ အထဲမှာ render လုပ်ပေးထားပါတယ်
- App component ကို PARENT component လို့ သတ်မှတ်ပြီး သူ့အထဲမှာ ခေါ်သုံးခံရတဲ့ component တွေကိုတော့ child component အဖြစ် သတ်မှတ်ပါတယ်
- အခု react app မှာသွားကြည့်မယ် ဆိုရင် Menu component မှာ return လုပ်ထားတဲ့ h1 tag ကို ပါ ပြပေးနေတာကို မြင်ရမှာဖြစ်ပါတယ်

##

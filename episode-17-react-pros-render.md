### Props in react component

- Props ဆိုတာ က parant component ကနေ child component ဆီကို data တွေ ပို့ချင်တဲ့အခါ အသုံးပြုပါတယ်
- parant component ကနေ props အနေနဲ့ ပို့လိုက်တဲ့ data တွေဟာ child component ဆီမှာ object parameter အနေနဲ့ လက်ခံပြီး အသုံးပြုလို့ရပါတယ်
  ### example

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

      <Menu name="Mont Him Khar" />
    </div>
  );
};

export default App;
```

- App component မှာ Menu component ကို ခေါ်သုံးတဲ့အချိန် props အနေနဲ့ name ဆိုတဲ့ data တစ်ခုကို ထည့်ပြီး ေခါ်ထားလိုက်ပါတယ်
- အဲ့ဒါဆိုရင် Menu component မှာလည်း အဲ့ဒီ props ကို လက်ခံရမှာ ဖြစ်ပါတယ်

```JS
// Menu.tsx

import React from "react";

interface Props {
  name: string;
}

// props = {name : "Mont Him Khar"}

const Menu = (props: Props) => {
  return (
    <div>
      <h1>Menu Component</h1>
      <h2>Data from props = {props.name}</h2>
    </div>
  );
};

export default Menu;

```

- props ကို parameter အနေနဲ့ လက်ခံထားပြီး props နဲ့ အတူပါလာတဲ့ data ကို h2 tag နဲ့ ပြပေးထားတာဖြစ်ပါတယ်

> Note
>
> - component တစ်ခုက prop ကို လက်ခံထားရင် အဲ့ဒီ component ကို import လုပ်သုံးတဲ့အခါ prop ကို ထည့်ပေးရပါမယ်
> - တစ်နည်း ။ ။ component တစ်ခုကို ကို import လုပ်သုံးတဲ့အခါ prop ကို ထည့်ပေးထားတယ်ဆိုရင် အဲ့ဒီ component မှာ props ကို မဖြစ်မနေ လက်ခံပေးရမှာ ဖြစ်ပါတယ်

##

### Sending more than one props

- parent component ကနေ child component ကို props တွေ အများကြီး ပို့လို့ရပါတယ်

```js
// App.tsx

import React from "react";
import Menu from "./components/Menu";

const App = () => {
  const name = "Mont Him Khar";
  const imgUrl =
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTndGXBpnkR8gS1I0Mf4Z5OLZygg5qwRIS6rA&usqp=CAU";

  return (
    <div>
      <div>{name}</div>
      <h1>Hello World</h1>

      <Menu name={name} price={2000} imgUrl={imgUrl} />
    </div>
  );
};

export default App;
```

```js
// Menu.tsx

import React from "react";

interface Props {
  name: string;
  price: number;
  imgUrl: string;
}

/*
props = {
  name: "Mont Him Khar",
  price: 2000,
  imgUrl:
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTndGXBpnkR8gS1I0Mf4Z5OLZygg5qwRIS6rA&usqp=CAU",
};
*/

const Menu = ({ name, price, imgUrl }: Props) => {
  return (
    <div>
      <h1>Menu Component</h1>

      <h2>Data from props</h2>
      <img src={imgUrl} alt="" />
      <div>{name}</div>
      <div>{price}</div>
    </div>
  );
};

export default Menu;
```

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146676074059681892/image.png)

##

### Using js function in react

- react component တစ်ခုက return ထဲမှာ js expression တွေ သုံးချင်ရင် `{ }` ထဲမှာ ထည့်ရေးပေးရတာကို ပြောပြခဲ့ပါတယ်
- ခု array တစ်ခု ကို map လုပ်ပြီး retrun မှာ render လုပ်တာကို လေ့လာကြည့်ရအောင်

```js
// App.tsx

import React from "react";
import Menu from "./components/Menu";

const App = () => {
  const menus = [
    {
      name: "Mont Him Khar",
      price: 2000,
      imgUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTndGXBpnkR8gS1I0Mf4Z5OLZygg5qwRIS6rA&usqp=CAU",
    },
    {
      name: "Hambuger",
      price: 3000,
      imgUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTndGXBpnkR8gS1I0Mf4Z5OLZygg5qwRIS6rA&usqp=CAU",
    },
    {
      name: "Sandwish",
      price: 4000,
      imgUrl:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTndGXBpnkR8gS1I0Mf4Z5OLZygg5qwRIS6rA&usqp=CAU",
    },
  ];

  return (
    <div>
      <h1>Hello World</h1>

      <Menu menus={menus} />
    </div>
  );
};

export default App;
```

- menus array တစ်ခု လုပ်ထားပြီး Menu component ကို ခေါ်တဲ့အခါ props အနေနဲ့ ထည့်ပေးလိုက်ပါတယ်

```js
// Menu.tsx

import React from "react";

interface Menu {
  name: string;
  price: number;
  imgUrl: string;
}
interface Props {
  menus: Menu[];
}

const Menu = ({ menus }: Props) => {
  return (
    <div>
      <h1>Menu Component</h1>

      <h2>Data from props</h2>
      {menus.map((menu, index) => {
        return (
          <div key={index}>
            <img src={menu.imgUrl} />
            <div>{menu.name}</div>
            <div>{menu.price}</div>
          </div>
        );
      })}
    </div>
  );
};

export default Menu;
```

- props အနေနဲ့ ၀င်လာမယ့် menus array ကို Menu component မှာ လက်ခံပြီး map လုပ်ကာ ပြသပေးထားပါတယ်
- react မှာ map method ကို သုံးလို့ရှိရင်

  - jsx ကို return ပြန်လုပ်ချင်ရင် return keyword ကို သုံးပေးရပါမယ်
  - return လုပ်ထားတဲ့ element မှာ key attribute ကို လည်း ထည့်ပေးရပါမယ်

- ခု react app မှာ သွားကြည့်ပါက အောက်ကလို ပြပေးနေမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146682934322003978/image.png)

##

### Styling react jsx element

- react element တွေကို style လုပ်ချင်ရင်

  - inline CSS
  - external CSS
  - CSS framework
  - React UI components

- စတာတွေ သုံးပြီး လုပ်လို့ရပါတယ်

### Inline CSS

- react component မှာ style attribute နဲ့ internal css ထည့်ရေးလို့ရပါတယ်
- ထူးခြားချက်အနေနဲ့ css property name တွေမှာ `-` ကို သုံးလို့မရပဲ camelcase နဲ့ ရေးပေးရမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1146685277390254191/image.png)

- ပုံထဲမှာ menu image ကို inline css နဲ့ style လုပ်ထားပါတယ်

```jsx
<img style={{ width: "200px", borderRadius: "50%" }} src={menu.imgUrl} />
```

- style attribute ကို သုံးတဲ့အခါမှာ `{{ }}` နဲ့ အသုံးပြုရမှာ ဖြစ်သလို
- css value တွေကို `" "` ထဲမှာ ထည့်ရေးပါမယ်
- property တစ်ခု ထပ်ပိုသုံးချင်ရင် `,` ခံပြီးရေးပေးရပါမယ်

### External CSS

- react element တွေကို class name ပေးပြီး style လုပ်လို့ရပါတယ်
- html element မှာလို `class=""` လို့ သုံးလို့ရမှာ မဟုတ်ပဲ `className=""` လို့ ရေးပေးရမှာ ဖြစ်ပါတယ်

```js
// Menu.tsx

import React from "react";

interface Menu {
  name: string;
  price: number;
  imgUrl: string;
}
interface Props {
  menus: Menu[];
}

const Menu = ({ menus }: Props) => {
  return (
    <div>
      <h1>Menu Component</h1>

      <h2>Data from props</h2>
      {menus.map((menu, index) => {
        return (
          <div className="menuCard" key={index}>
            <img
              style={{ width: "200px", borderRadius: "50%" }}
              src={menu.imgUrl}
            />
            <div className="name">{menu.name}</div>
            <div className="price">{menu.price}</div>
          </div>
        );
      })}
    </div>
  );
};

export default Menu;
```

- ပေးထားတဲ့ class name တွေ သုံးပြီး css ဖိုင်တစ်ခုမှာ style လုပ်ပါမယ်
- src folder အောက်မှာ styles folder တစ်ခုလုပ်ပါမယ်
- အဲ့ဒီ folder ထဲမှာ menuStyle.css ဖိုင်တစ်ခုလုပ်ပါမယ်

```js
.menuCard {
  width: 200px;
  height: 200px;
  border: 1px solid black;
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 5%;
  margin: 0.5rem;
  cursor: pointer;
  padding: 5px;
}

.menuCard:hover img {
  transform: scale(1.1) rotateX(20deg); /* Apply scale and rotation on hover */
  box-shadow: 4px 4px 4px black; /* Adjust box-shadow on hover */
}

.menuCard:hover {
  background-color: rgba(0, 0, 0, 0.2);
}
.menuCard:hover .name {
  transform: scale(1.1);
  text-shadow: 1px 1px 2px black;
}
```

- ခု အဲ့ဒီ css file ကို Menu component ထဲမှာ import လုပ်ပေးရပါမယ်
- ထူးခြားချက်အနေနဲ့ အခြား import တွေလို from တွေ ဘာတွေ ထည့်စရာမလိုပဲ direct import လုပ်ပေးရမှာဖြစ်ပါတယ်
  ![](https://cdn.discordapp.com/attachments/1146496852087287898/1146690844372508683/image.png)
  - line 4 မှာ external css file ကို direct import လုပ်ထားတာဖြစ်ပါတယ်

##

### MUI ဆိုတာက design လုပ်ပြီးသား အသင့်သုံးလို့ရတဲ့ react UI component တွေ ဖြစ်ပါတယ်

- mui ဆိုတာက Material UI ကို အတိုကောက် ခေါ်တာဖြစ်ပြီး
- Material UI ဆိုတာ open-source React component library တစ်ခုဖြစ်ပြီး Google ရဲ့ Material Design ကို အသုံးပြုထားတာဖြစ်ပါတယ်။
- mui ကို သုံးနိုင်ရန် npm နဲ့ project ထဲ install လုပ်ပေးရပါမယ်။

```console
$ npm install @mui/material @emotion/react @emotion/styled @mui/icons-material
```

##

### using mui app-bar

- mui appbar တစ်ခုကို အသုံးပြုကြည့်ပါမယ်
- https://mui.com/material-ui/react-app-bar/ ကိုသွားလိုက်ပါ

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148132845164974080/image.png)

- show code ကို နှိပ်လိုက်ရင် အပေါ်က component ရဲ့ code တွေ ပြပေးမှာ ဖြစ်ပါတယ်
- အဲ့ထဲ့ကမှ Box compopnent တစ်ခုလုံး ကူးလိုက်ပါမယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148133039352860753/image.png)

- Box ဆိုတာ mui မှာပါတဲ့ component တစ်ခု ဖြစ်ပြီး html က div တစ်ခုနဲ့ တူပါတယ်
- sx ဆိုတာ mui component တွေကို inline css ရေးလို့ရနိုင်တဲ့ props တစ်ခု ဖြစ်ပါတယ်။
- ကူးယူလာတဲ့ code တွေကို react project ထဲက App component ထဲ ထည့်ပြီး လိုအပ်တာတွေ import လုပ်ပေးရပါမယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148134428044963840/image.png)

- error ပြနေတဲ့ နေရာတွေမှာ ေထာက်ပြီး တစ်ခုချင်းစီ import လုပ်ပေးရပါမယ်
  ![](https://cdn.discordapp.com/attachments/1146496852087287898/1148134614402093086/image.png)

  - Add all missing import ကို လဲ သုံးနိုင်ပါတယ်
  - အဲ့ဒါဆိုရင် လိုအပ်တဲ့ import တွေကို auto ရှာပြီး ထည့်ပေးလိုက်မှာ ဖြစ်ပါတယ်
  - တစ်ခုသတိထားရမှာက Add all missing import က တစ်ခါတရံ လွဲတက်တာမလို့ သူ့ကို သုံးပြီးတိုင်း import တွေကို ပြန်စစ်သင့်ပါတယ်

  ##

  ## render in react

### react မှာ component တစ်ခုဟာ အဓိက အားဖြင့်

1. Props change ချိန်းလိုက်ရင်
2. သူ့ကို ထိန်းထားတဲ့ parent component က ren-render ပြန်လုပ်ရင်
3. State ချိန်းလိုက်ရင်

### re-render ( တစ်ခါပြန်run) လုပ်ပေးပါတယ်

- အခု ဒါကို နမူနာကြည့်ရအောင်
- App.jsx နဲ့ User.jsx မှာ log တစ်ခုဆီ ထုတ်ထားပါမယ်

```js
// App.jsx
import User from "./components/User";

const App = () => {
  console.log("App component rendered...");
  return (
    <div className="App">
      <User userName="user1" email="user1@gmial.com" />
    </div>
  );
};

export default App;
```

```js
// User.jsx
const User = (props) => {
  console.log("User component rendered...");
  return (
    <div>
      <h1>User name is {props.userName}</h1>
      <h1>email is {props.email}</h1>
    </div>
  );
};

export default User;
```

- ခု ကျနော်တို့ react app ကို refresh လုပ်ကြည့်လိုက်တဲ့အခါ console မှာ App component နဲ့ User component ကို render လုပ်ပေးတာကို မြင်ရမှာဖြစ်ပါတယ်။

![enter image description here](https://raw.githubusercontent.com/Aungmyanmar32/msquare-m4/main/Screenshot%202023-03-25%20230139.png)

> မှတ်ချက် ။ ။ log နှစ်ခုစီ ထုတ်ပေးနေပါက index.js မှာ အောက်ပါအတိုင်း ပြင်ပေးလိုက်ပါ။

```js
// index.js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <>
    <App />
  </>
);
```

- ခု App.jsx မှာ တစ်ခုခု ပြင်ကြည့်လိုက်ပါက App component သာမကသူ့အထဲမှာ render လုပ်ထားတဲ့ child component ဖြစ်တဲ့ User component ပါ re-render ဖြစ်သွားတာကို မြင်ရမှာပါ။

```js
// console output

App component rendered...
User component rendered...
App component rendered...
User component rendered...
```

##

### React Hook

- react မှာ hook ဆိုတာ function တစ်မျိုးပဲ ဖြစ်ပြီး state တွေကို ထိန်းချုပ်နိုင်ဖို့အတွက် အသုံးပြုကြပါတယ်။

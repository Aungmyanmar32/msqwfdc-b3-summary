## MSquare Programming Fullstack Course

### Batch 2

### Episode-_12_ Summary

- MUI
- useState
- render in react
- useEffect

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

### State in react

- state ဆိုတာ react component တစ်ခုရဲ့ လက်ရှိအခြေအနေ ကို ဆိုလိုတာဖြစ်ပါတယ်။
- react ကို functional component နဲ့ ရေးတဲ့အခါ state တွေ သုံးလို့ရအောင် hook တွေနဲ့ ချိတ်ပေးရပါတယ်။
- react hook ဆိုတာကလည်း function တစ်မျိုးလို့ သတ်မှတ်နိုင်ပါတယ်။

##

### useState hook

syntax
`const [ state , set-function] = useState(initialState) `

- **state** ဆိုတဲ့ နေရာမှာ useState ရဲ့ နောက် **(initialState ) ထဲက တန်ဖိုး** ၀င်လာမှာ ဖြစ်ပြီး၊
- **set-function** ကတော့ ရှေ့က **state** တန်ဖိုးကို **updateလုပ်တဲ့ function**လို့ အကြမ်းဖျင်းမှတ်သားထားပါ။

### Example code

    const [number ,setNumber] = useState(1)

##

### Using useState() hook in react

```js
// App.jsx

import { useState } from "react";
import User from "./components/User";

const App = () => {
  const num1 = 30;
  const [name, setName] = useState("Aung");
  console.log("App component rendered...");
  return (
    <div className="App">
      <h1>My name is {name}</h1>
      <button onClick={() => setName("Myanmar")}>Click Me</button>
    </div>
  );
};

export default App;
```

> ရှင်းလင်းချက်

`import { useState } from "react";`

- useState hook ကို အသုံးပြုမှာမလို့ import လုပ်ထားပါတယ်

`const [name, setName] = useState("Aung");`

- useState hook ကို ကြေငြာထားပါတယ်
- ခု အချိန်မှာတော့ name ရဲ့ တန်ဖိုးက Aung ဖြစ်ပါတယ်။

```
return (
    <div className="App">
      <h1>My name is {name}</h1>
      <button onClick={() => setName("Myanmar")}>Click Me</button>
    </div>
  );
```

- return လုပ်ထားတဲ့နေရာမှာ name ရဲ့ တန်ဖိုးကို h1 tag အထဲ ယူသုံးထားပါတယ်
- Click Me button တစ်ခုလဲလုပ်ထားပြီး အဲ့ဒီခလုတ်ကို နှိပ်လိုက်တဲ့ အခါ useState hook ထဲက setName ဆိုတဲ့ function ကို ခေါ်လိုက်ပြီး မူလstate ရဲ့ တန်ဖိုး ( Aung) ကို (Myanmar) အဖြစ်သို့ update လုပ်ခိုင်းထားပါတယ်
- react app ကို start လိုက်တဲ့အခါ အောက်ပါအတိုင်းအရင်ပြပေးမှာဖြစ်ပါတယ်။
- ![enter image description here](https://raw.githubusercontent.com/Aungmyanmar32/msquare-m4/main/Screenshot%202023-03-26%20000012.png)
- Click Me ခလုတ်ကို နှိပ်လိုက်ပါက state update ဖြစ်ပြီး အောက်ပါအတိုင်း ပြပေးမှာဖြစ်ပါတယ်

![enter image description here](https://raw.githubusercontent.com/Aungmyanmar32/msquare-m4/main/Screenshot%202023-03-26%20000244.png)

- console ထဲမှာ လဲ re-render တစ်ခါ ထပ်လုပ်ပေးသွားတာကို မြင်ရမှာပါ။
- react မှာ state ပြောင်းလဲမှု ရှိရင် ထို component ကို re-render လုပ်ပေးတာမို့လို့ ဖြစ်ပါတယ်။

##

### update object state using mui TextField

- mui TextField ရဲ့ onChange event ကို သုံးပြီး object state တစ်ခုကို update လုပ်ကြည့်ပါမယ်

```js
//Menu.tsx

import { useEffect, useState } from "react";

import { Box, Button, TextField } from "@mui/material";

const Menu = () => {
  const message = "Hello World";

  //useState -- react hook -- function -- state
  // const [state , update-state-function ] = useState(init-state-value) / init-v = 0 , state = 0

  //re-render
  // - state change
  // - props change

  const [menu, setMenu] = useState({ name: "", price: 0 });
  //menu = { name: "", price: 0 }

  const handleCreate = () => {
    console.log(menu);
  };

  return (
    <Box>
      <Box>
        <TextField
          type="text"
          placeholder="name"
          onChange={(e) => setMenu({ ...menu, name: e.target.value })}
        />
        <TextField
          type="number"
          placeholder="price"
          onChange={(e) => setMenu({ ...menu, price: Number(e.target.value) })}
        />
        <Button variant="contained" onClick={handleCreate}>
          Create
        </Button>
      </Box>
    </Box>
  );
};

export default Menu;
```

> ရှင်းလင်းချက်

```js
const [menu, setMenu] = useState({ name: "", price: 0 });
```

- menu state တစ်ခုလုပ်ထားပြီး မူလအခြေအနေ တန်ဖိုးအနေနဲ့ { name: "", price: 0 } ကို သတ်မှတ်ပေးထားပါတယ်

```js
const handleCreate = () => {
  console.log(menu);
};
```

- handleCreate function တစ်ခုသတ်မှတ်ထားပြီး အထဲမှာ menu state ကို log ထုတ်ကြည့်ထားပါတယ်

```js
<TextField
  type="text"
  placeholder="name"
  onChange={(e) => setMenu({ ...menu, name: e.target.value })}
/>
```

- Mui TextFile ကို သုံးထားပြီး တစ်ခုခု ပြောင်းလဲမှု ရှိခဲ့ရင် setMenu function နဲ့ menu state ထဲက name ရဲ့တန်ဖိုးကို update လုပ်လိုက်တာဖြစ်ပါတယ်
- ဒီနေရာမှာ string ကို update လုပ်လိုက်သလိုမျိုး တစ်ခါတည်း အသစ်ထည့်ပေးလိုက်သလို လုပ်လို့မရပါဘူး
- react မှာ object state တစ်ခုကို update လုပ်မယ်ဆိုရင် မူလ object ကို အရင် copy (`{...object-name}`) လုပ်ပြီးမှ အဲ့ဒီ object ထဲက တန်ဖိုးပြောင်းချင်တဲ့ property name ကို အသုံးပြုပြီး တန်ဖိုးအသစ် သတ်မှတ်ပေးရမှာဖြစ်ပါတယ်
- နမူနာထဲမှာဆိုရင်

`onChange={(e) => setMenu({ ...menu, name: e.target.value })}`

- မူလ menu state ကို copy ကူးပြီးမှ menu state ထဲက name ရဲ့တန်ဖိုးကို user က ရိုက်ထည့်လိုက်တဲ့ တန်ဖိုးနဲ့ update လုပ်လိုက်တာဖြစ်ပါတယ်

```js
<TextField
  type="number"
  placeholder="price"
  onChange={(e) => setMenu({ ...menu, price: Number(e.target.value) })}
/>
```

- အပေါ်က လိုပဲ menu state ထဲက price ရဲ့ တန်ဖိုးကို user ထည့်လိုက်တဲ့ တန်ဖိုးနဲ့ update လုပ်ပေးလိုက်တာပဲဖြစ်ပါတယ်
- ခု react app မှာ စမ်းသပ်ကြည့်ပါက update ဖြစ်တဲ့ menu state ကို create button ကို နှိပ်လိုက်ရင် log ထုတ်ပေးမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148147390633758800/image.png)

##

### useEffect hook

- useEffect ဆိုတာက react compoent တစ်ခု render လုပ်ပြီးတဲ့အချိန်မှာ အခြားလုပ်ဆောင်ချက်တစ်ခုကို လုပ်ခိုင်းချင်တဲ့အခါ သုံးလေ့ရှိပါတယ်

### syntax

`useEffect(callback-function , dependecy-list[])`

- useEffect ကို သုံးမျိူး သုံးလို့ရပါတယ်
  - `useEffect(callback-function)`
  - `useEffect(callback-function,[])`
  - `useEffect(callback-function,[state])`

### `useEffect(callback-function)`

- dependency list မပါပဲ callback function တစ်ခုပဲ parameter ထည့်ပေးထားပါတယ်

### example

```js
import { useEffect, useState } from "react";
import Menu from "./components/Menu";

import MenuIcon from "@mui/icons-material/Menu";
import {
  Box,
  AppBar,
  Toolbar,
  IconButton,
  Typography,
  Button,
} from "@mui/material";

const App = () => {
  const [count, setCount] = useState(0);
  const [count2, setCount2] = useState(0);

  useEffect(() => {
    console.log("inside use effect");
  });

  console.log("outside");
  console.log("outside");
  console.log("under use effect");
  console.log("render.....");
  console.log("outside");

  const handleCount = () => {
    let i = count + 1;
    setCount(i);
    console.log("render.... by count");
  };

  const handleCount2 = () => {
    let i = count2 + 1;
    setCount2(i);
    console.log("render.... by count");
  };

  return (
    <Box>
      <Box sx={{ flexGrow: 1 }}>
        <AppBar position="static">......</AppBar>

        <h1>{count}</h1>
        <Button variant="outlined" onClick={handleCount}>
          Count
        </Button>

        <h1>count2 {count2}</h1>
        <Button variant="outlined" onClick={handleCount2}>
          Count2
        </Button>
      </Box>
      <Menu />
    </Box>
  );
};

export default App;
```

- useEffect hook ကို သုံးထားပြီး inside use effect ကို log ထုတ်ထားပါတယ်
- useEffect အပြင်အောက်မှာေတာ့ outside log တွေ ထုတ်ထားပါတယ်
- အခု react app ကို run ကြည့်လိုက်တဲ့အခါ
- react script က App component ကို အစဥ်တိုင်း ဖတ်လာပြီး useEffect ကို ရောက်တဲ့အခါ run ပေးမှာမဟုတ်သေးပဲ ဆက်သွားလိုက်ပါတယ်
- component တစ်ခုလုံး render လုပ်ပြီးသွားမှ useEffect ထဲက code တွေကို လာပြန်ပြီး run ပေးမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148153480582799401/image.png)

- ပုံထဲမှာ inside use effect က ေနာက်ဆုံးမှ log ထုတ်ပေးတာကို မြင်ရမှာဖြစ်ပါတယ်
- ကျနော်တို့ count button ကို နှိပ်ပြီး count state ကို ချိန်ကြည့်ပါမယ်
- state ချိန်းရင် react component က re-render လုပ်တာမလို့ log တွေ ထပ်ထွက်လာတာကို မြင်ရမှာဖြစ်ပါတယ်
- ထို့အတူပဲ useEffect လဲ တစ်ခါပြန်run ပေးတာကို မြင်ရမှာပါ

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148154457385873468/image.png)

- useEffect မှာ

```js
useEffect(() => {
  console.log("inside use effect");
});
```

- callback function တစ်ခုပဲ ထည့်ခေါ်ထားတယ် ဆိုရင် component က re-render ဖြစ်တိုင်း useEffect လဲ တစ်ခါပြန်run ပေးမှာဖြစ်ပါတယ်

### `useEffect(callback-function,[])`

- ဒီတစ်ခါတော့ useEffect ကို callback ကော dependency list အနေ နဲ့ empty array [ ] ကို ထည့်ပေးပြီး သုံးကြည့်ပါမယ်

```js
useEffect(() => {
  console.log("inside use effect");
}, []);
```

- react app ကို refresh လုပ်ကြည့်ပါက ပုံမှန်အတိုင်းပဲ component ပထမ အကြိမ် render ဖြစ်တဲ့အချိန် useEffect လဲ run ပေးမှာဖြစ်ပါတယ်
- ဒါပေမယ့် state တစ်ခုခုကို update လုပ်ကြည့်လိုက်တဲ့အခါ component က render ဖြစ်သွားပေးမယ့် useEffect က ထပ်ပြီး မ run တော့တာကို မြင်ရမှာဖြစ်ပါတယ်
- အောက်က ပုံ ထဲကလို count state ကို update လုပ်ကြည့်ပါက component က render ဖြစ်ပြီး useEffect အပြင်က log တွေ ထုတ်ပေးလာေသာ်လည်း useEffect ထဲက log ထုတ်ပေးခြင်းမရှိတာကို မြင်ရမှာဖြစ်ပါတယ်

![](https://cdn.discordapp.com/attachments/1146496852087287898/1148164372242386974/image.png)

- **`useEffect(callback-function,[])` က ပထမအကြိမ် render ဖြစ်တဲ့အချိန်မှာသာ တစ်ခါပဲ run ပေးမှာဖြစ်ပြီး re-render ထပ်ဖြစ်တဲ့အခါ ထပ်ပြီး run ပေးမှာ မဟုတ်ပါ**

### `useEffect(callback-function,[state])`

- ဒုတိယ နည်းလမ်းတဲ့ မတူတာက dependency list array ထဲမှာ state တစ်ခုခုကို ထည့်ပေးလိုက်ရင် အဲ့ဒီ state ကို useEffect က စောင့်ကြည့်နေမှာဖြစ်ပြီး ARRAY ထဲက state ချိန်းတိုင်း useEffect က တစ်ခါပြန် run ပေးမှာဖြစ်ပါတယ်

```js
useEffect(() => {
  console.log("inside use effect");
}, [count2]);
```

- useEffect မှာ callback-function ရော dependency list array ပါထည့်ခေါ်ထားပြီး dependency list array ထဲမှာ `count2` state ကို ထည့်ပေးလိုက်ပါတယ်

- useEffect က count2 ကိုပဲ စောင့်ကြည့်နေမှာဖြစ်ပြီး ကျန်တဲ့ state တွေ ချိန်းလို့ component က re-render ဖြစ်တဲ့အခါ useEffect က ထပ် run မှာ မဟုတ်ပဲ array ထဲက count2 update ဖြစ်တဲ့အခါမှသာ run ပေးတော့မှာ ဖြစ်ပါတယ်

- **`useEffect(callback-function,[state])` က ပထမအကြိမ် render ဖြစ်တဲ့အချိန်မှာသာ တစ်ခါပဲ run ပေးမှာဖြစ်ပြီး re-render ထပ်ဖြစ်တဲ့အခါ dependency list ထဲက state update မဖြစ်ဘူးဆိုရင်ထပ်ပြီး run ပေးမှာ မဟုတ်ပါ။ dependency list ထဲက state updateဖြစ်မှသာ ထပ်runမှာ ဖြစ်ပါတယ်**

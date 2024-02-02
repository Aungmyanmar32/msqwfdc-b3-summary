### Response html file when request method is "GET"

- frontend ကနေ GET method နဲ့ request ၀င်လာတဲ့အခါ html file တစ်ခု ကို ဖတ်ပြီး response ပြန်ပေးလိုက်တာကို လေ့လာကြည့်ရအောင်။
- အရင်ဆုံး index.html ဖိုင်တစ်ခုလုပ်လိုက်ပါမယ်

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Html response ......</h1>
  </body>
</html>
```

- ပြီးရင် http server မှာ request ကို လက်ခံတဲ့အခါ အဲ့ဒီ index.html ဖိုင်ကို ဖတ်ပြီး reponse ပြန်ပေးလိုက်ပါမယ်

```js
//server.ts

import fs from "fs";
import http, { IncomingMessage, ServerResponse } from "http";
import nanoid from "nanoid";
import { Menu, MenuCategory } from "./types";

let menus: Menu[] = [];
const menuCategories: MenuCategory[] = [];

const PORT = 3000;
const server = http.createServer(
  (req: IncomingMessage, res: ServerResponse) => {
    const url = req.url;
    const method = req.method;
    if (url === "/") {
      const data = fs.readFileSync("index.html");
      res.write(data);
      res.end();
    } else if (url === "/script.js") {
      const data = fs.readFileSync("script.js");
      res.write(data);
      res.end();
    } else if (url === "/menu-category") {
    }
  }
);

server.listen(PORT, () => console.log(`Server started listening on: ${PORT}`));
```

- ရှင်းလင်းချက်

```js
if (url === "/") {
  const data = fs.readFileSync("index.html");
  res.write(data);
  res.end();
}
```

- url က "/" ဖြစ်ခဲ့ရင်
- fs readFile method ကို သုံးပြီး index.html ကို ဖတ် လိုက်ပါတယ်
- `response.write(data);` ကတော့ readFile လုပ်ပြီး ထွက်လာတဲ့ data တွေကို response body ထဲကို write လုပ်လိုက်တာဖြစ်ပါတယ်
- `return response.end();` ဒါကတော့ request ကို လက်ခံပြီး response ပြန်ပေးခြင်း ပြီးဆုံးပြီ ဖြစ်ကြောင်း သတ်မှတ်လိုက်တာပါ
- node js server မှာ response ပြန်တဲ့ လုပ်ငန်းစဥ် ပြီးဆုံးတိုင်း response.end() method ကို မဖြစ်မနေ ထည့်ရေးပေးရမှာဖြစ်ပါတယ်
- ခု browser ကနေ GET method နဲ့ request send ကြည့်ပါမယ်

- html ထဲမှာ ရေးထားတဲ့ h1 tag ကို response ပြန်ပေးတာကို မြင်ရမှာဖြစ်ပါတယ်။

##

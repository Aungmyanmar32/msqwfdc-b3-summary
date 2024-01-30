### setTimeout()

လုပ်ဆောင်ချက်တစ်ခုကို အချိန်တစ်ခု သတ်မှတ်ထားပေးပြီး သတ်မှတ်ထားတဲ့ အချိန်ရောက်မှ အလုပ်လုပ်ခိုင်းတာပါ။

#### Syntax

`setTimeout`(`callback-function`, `delay-time`)

#### Usage

```js
setTimeout(() => {
  console.log("Delayed for 1 second.");
}, 1000);
//အချိန် 1000ms(တစ်စက္ကန့်)ကြာပြီးမှ console.log ကို run ပေးပါ။
```

1000 = 1000 milli second = 1 second

##

### Promise

callback function တွေကဲ့သို့ အရင်လုပ်နေတဲ့ လုပ်ဆောင်ချက်တွေ မပြီးမချင်း စောင့်ပြီးမှ အလုပ်လုပ်စေချင်တဲ့အခါ အသုံးပြုလေ့ရှိပါတယ်။<br>
`Network Request` , `Data respond` တွေ စောင့်ပြီးမှ ဆက်လက်လုပ်ဆောင်ရမယ့်အခါ **promise**ကို သုံးရပါတယ်။
<br>

### Syntax

`promise-Name` `=` `new Promise` ((`fulfill`,`reject`) `=>{`Do somethings..`};`

![enter image description here](https://cdn.programiz.com/sites/tutorial2program/files/javascript-promise.png)
<br>
ပုံကို လေ့လာကြည့်ရင် promise တစ်ခု

- ပြီးမြောက်(fulfill/ **resolve**) သွားပါက **.then()** **method** ကို ဆက် run မှာ ဖြစ်ပြီး
- မပြီးမြောက်(**reject**/error )ပါက **.catch() method** ကို သွား run ပေးမှာပါ။

#### example-1 resolve(**result**) > .then(**result**)

```js
const countValue = new Promise((resolve, reject) => {
  resolve("Promise resolved");
});

countValue
  .then((result) => {
    console.log("the result from resolve is", result);
  })
  .catch((error) => {
    console.log(error);
  });
//output: the data from resolve is Promise resolved
```

#### example-2 reject(**error**) > .catch(**error**)

```js
const countValue = new Promise((resolve, reject) => {
  reject("promise rejected");
});

countValue
  .then((data) => {
    console.log("the result from resolve is", result);
  })
  .catch((error) => {
    console.log("error from reject is", error);
  });
//output: error from reject is promise rejected
```

##

##

- Promise တစ်ခု resolve ဖြစ်တဲ့အခါ .then ထဲက callback function က အလုပ်လုပ်ပြီး promise တစ်ခုကို return ပြန်ထုတ်ပေးတယ်ဆိုပါစို့။
- ထို ပြန်ထုတ်ပေးတဲ့ promise ကို ဆက်ပြီး .then . catch နဲ့ ဆက်ပြီး ချိတ်ဆက်အသုံးပြုတာကို promise chaining လို့ ခေါ်ပါတယ်
  > Enample

```js
new Promise((resolve, reject) => {
  resolve("this is reslove 1");
})
  .then((data) => {
    console.log(data);
    new Promise((resolve, reject) => {
      resolve("this is reslove 2");
    })
      .then((data) => {
        console.log(data);
        new Promise((resolve, reject) => {
          resolve("this is reslove 3");
        })
          .then((data) => {
            console.log(data);
            new Promise((resolve, reject) => {
              resolve("this is reslove 4");
            })
              .then((data) => {
                console.log(data);
              })
              .catch((error) => {
                console.log(error);
              });
          })
          .catch((error) => {
            console.log(error);
          });
      })
      .catch((error) => {
        console.log(error);
      });
  })
  .catch((error) => {
    console.log(error);
  });
//output 1: this is reslove 1
//output 2: this is reslove 2
//output 3: this is reslove 3
//output 4: this is reslove 4
```

- အထက်ပါ ကုဒ်ကို လေ့လာကြည့်ပါက ရှုပ်ထွေးနေပြီး နားလည်ရ ခက်စေပါတယ်။
  ဒီလို .then .catch တွေနဲ့ ရှုပ်ထွေးနေတဲ့ promise ကို **promise hell** လို့ ခေါ်ပါတယ်။
- coding မှာ promise hell, callback hell , if/esle hell တွေ ရှိနေရင် ကောင်းမွန်တဲ့ code တစ်ခုလို့
  သတ်မှတ်လို့ မရပါဘူး။ Coding လုပ်သူကိုယ်တိုင် နားလည်ရခက်စေပြီး အခြားသူများလဲ ကြည့်ရှုစစ်ဆေးရန် အဆင်မပြေ ဖြစ်ရပါတယ်။
- ကောင်းမွန်တဲ့ code တစ်ခုဆိုတာ ယေဘုယျ အားဖြင့်

1. clean and clear ဖြစ်ရပါမယ်
2. code တွေ ထပ်နေတာမျိုး မဖြစ်သင့်ပါဘူး (**_DRY_**- **D**on't **R**epeat **Y**ourself)
3. မိမိကိုယ်တိုင်သာမက အခြားသူများလဲ နားလည်ရ လွယ်စေမယ့် ပုံစံမျိုးလဲ ဖြစ်ရပါမယ်

- Promise Hell ကို ဖြေရှင်းရန် async/await function ကို အသုံးပြုလေ့ရှိပါတယ်
  

##

### fetch

### fetch ဆို javascript မှာ အသင့်ပါလာတဲ့ method တစ်ခုဖြစ်ပါတယ်

### fetch မှာ

- server ကနေ data တွေ လှမ်းယူခြင်း (**GET** method)
- server ဆီသို့ data အသစ်တွေ ပို့ခြင်း(**POST** method)
- server က data တွေကို ပြင်ဆင်ခြင်း(**PUT** method)
- server က data တွေကို ဖျက်ခြင်း(**DELETE** method)
- စတဲ့ အဓိက method တွေ အပြင် အခြား အသုံး၀င်တဲ့ method တွေ ပါ၀င်ပါတယ်။

#### `Ftech` ကို back-end server နဲ့ ချိတ်ဆက်ပြီး data တွေ request လုပ်တဲ့အခါ အသုံးပြုလေ့ရှိကြပါတယ်။

-**fetch() method** က **promise တစ်ခုကို return** ပြန်ပေးပါတယ်။<br> -**promise တစ်ခုကို return** ပြန်ပေးတဲ့အခါ ယေဘုယျ အနေနဲ့ **resolve ကို auto သတ်မှတ်**ပေးပါတယ်။

#### Syntax

    fetch(url,{method});

#### Usage

```js
const url = "https://fakestoreapi.com/products";
fetch(url)
  .then((response) => response.json())
  .then((data) => console.log(data));

//(20) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}]
```

> ရှင်းလင်းချက်

```js
const url = "https://fakestoreapi.com/products";
```

- api server တစ်ခုရဲ့ လိပ်စာကို url variable အနေနဲ့ သိမ်းလိုက်တာပါ။

```js
fetch(url);
```

- ခုနက သိမ်းထားတဲ့ url ကနေ GET methodနဲ့ data လှမ်းယူလိုက်တာပါ
  ( fetch မှာ method ကို မထည့်ထားဘူးဆိုရင် default အနေနဲ့ GET method ဖြစ်ပါတယ်)
- fetch က fulfill promise(`resolve`) တစ်ခု return ပြန်ပေးတာမလို့ `.then()` သုံးလို့ရပါပြီ

```js
.then((response) => response.json())
```

- fetch က return ပြန်လာတဲ့ promise(response) ကို လက်ခံလိုက်ပြီး
  ထို response ထဲမှာ ပါလာတဲ့ json() method ကို အသုံးပြုလိုက်တာပါ
- ဒီ `.then` ကလဲ promise တစ်ခုကို return ပြန်ထုတ်ပေးပါတယ်။

```js
.then((data) => console.log(data));
```

- အထက်က ( .then ) က return ပြန်လာတဲ့ promise(data) ကို လက်ခံလိုက်ပြီး
  ထို data ထဲမှာ ရလာတဲ့ အချက်အလက်တွေကို console log ထုတ်လိုက်တာဖြစ်ပါတယ်။

##

### Using fetch and thrown error

```js
const url = "https://fakestoreapi.com/productsdfdfdsafdsa";

fetch(url)
  .then((response) => {
    response
      .json()
      .then((data) => {
        console.log(data);
      })
      .catch((err) => {
        console.log("Inside catch...", err);
      });
  })
  .catch((err) => {
    console.log("Outside catch: ", err);
  });
```

> Try it

ကျနော်တို့က url link ကို အမှားကြီး ပေးထားပြီး

1. catch() နှစ်ခုမှာ log နှစ်မျိုး ထုတ်ထားပါတယ်။
2. ပထမ console.log ကို .then တစ်ခုထဲ ထည့်ထားပါတယ်
3. ဒုတိယ console.log ကိုတော့ .then အနောက်မှာ လုပ်ထားပါတယ်

- အထက်ပါ code ကို စမ်းကြည့်တဲ့ အခါ
  မည်သည့် error (or) console.log ပေါ်လာမယ်လို့ သင်ထင်ပါလဲ။
- အရင်ဆုံး ကုဒ်ကို မစမ်းကြည့်ပဲ ဒီအတိုင်းစဥ်းစားပြီး အဖြေထုတ်ကြည့်ပါ။

##

## async/await function

### async/await function ဆိုတာကတော့

### ဥပမာ လုပ်ဆောင်ချက်သုံးခုရှိတယ် ဆိုပါစို့

### - နံပါတ်တစ် လုပ်ဆောင်ချက်ပြီး အောင် စောင့်ပြီးမှ

### -- နံပါတ်နှစ် လုပ်ဆောင်ချက် ကို ဆက်လုပ်....

### - -နံပါတ်နှစ် လုပ်ဆောင်ချက်ပြီးအောင် စောင့်ပြီးမှ

### --- နံပါတ်သုံး လုပ်ဆောင်ချက် ကို ဆက်လုပ်....

ဆိုပြီး အရင်လုပ်ခိုင်းတဲ့ လုပ်ဆောင်ချက်တွေ ပြီးအောင်စောင့်ပြီးမှ ကျန်တာ ဆက်လုပ်ခိုင်းချင်တဲ့အခါ သုံးလေ့ရှိပါတယ်။

### promise ကို အသုံးပြုရ လွယ်ကူစေရန် async/ await function နဲ့အစားထိုး အသုံးပြုလေ့ရှိပါတယ်

###

### Syntax

`async` ( ) => {
`await` step1-code
`await` step2-code
`await` step3-code
}

##

### Get data from api server

- api server ကနေ data များကို fetch ကို အသုံးပြုပြီး လှမ်းယူပုံကို အရင် သင်ခန်းစာမှာ လေ့လာခဲ့ပြီး ဖြစ်ပါတယ်။
-

```js
const getData = () => {
  const url = "https://fakestoreapi.com/products";
  const fetchData = fetch(url);
  fetchData
    .then((response) => response.json())
    .then((data) => console.log(data));
};
getData();
```

- အထက်ပါကုဒ်ကို async / await function နဲ့ အခုလို သုံးလို့ရပါတယ်

```js
const getData = async () => {
  const url = "https://fakestoreapi.com/products";
  const response = await fetch(url);
  const data = await response.json();
  console.log(data);
};

getData();
```

> ရှင်းလင်းချက်

```js
const getData = async() =>
```

- getDataဆိုတဲ့ function ကို async function ဖြစ်ကြောင်း သတ်မှတ်လိုက်ပါတယ်

```js
const url = "https://fakestoreapi.com/products";
```

- အသုံးပြုမယ့်ဆာဗာရဲ့ လိပ်စာကို url variable နဲ့ သိမ်းလိုက်တာပါ

```js
const response = await fetch(url);
```

- fetch ကနေ return ပြန်လာတဲ့ promise ကို response variable ထဲ သိမ်းလိုက်တာပါ။
- ဒီနေရာမှာ `await` က fetch အလုပ်လုပ်နေတာကို ပြီးအောင်စောင့်ပါလို့ အဓိပ္ပါယ် ရပါတယ်

```js
const data = await response.json();
```

- response က data တွေထဲ json dataကို လိုချင်တာမလို့ .json() နဲ့ လှမ်းယူလိုက်တာဖြစ်ပါတယ်။

##

### Catch error in async/ await Function

-async function မှာ error ဖြစ်လာခဲ့ရင် ဖမ်းယူဖို့အတွက် try{} catch{} နဲ့ အသုံးပြုရပါမယ်။

```js
const getData = async () => {
  try {
    const url = "https://fakestoreapi.com/productsffffff";
    const response = await fetch(url);
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("error occuerd", error);
  }
};
getData();
```

- ရေးထားတဲ့ ကုဒ်တွေကို `try { }` ထဲ ထည့်ထားလိုက်ပြီး error မရှိခဲ့ code ရေးထားတဲ့အတိုင်း အလုပ်လုပ်ခိုင်းထားတာဖြစ်ပြီး
- error ရှိလာရင်ခဲ့တော့ ဖြစ်တဲ့ error ကို `catch { }` ထဲ မှာ console.log ထုတ်ခိုင်းထားဖြစ်ပါတယ်
- အထက်ပါ code မှာ တော့ error မရှိတဲ့အတွက် try { } ထဲက code တွေ ရေးထားတဲ့အတိုင်း အလုပ် လုပ်နေမှာ ဖြစ်ပါတယ်

##

### Try to catch error

```js
const getData = async () => {
  try {
    const url = "https://fakestoreapi.com/productsffffff";
    const response = await fetch(url);
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("error occuerd :", error);
  }
};
getData();
```

- url ကို အမှားပေးထားပြီး error ကို catch လုပ်ကြည့်ထားတာဖြစ်ပါတယ်

### JavaScript Data Types

<table border="0"><tbody><tr><td>Data Types</td>
				<td>ရှင်းလင်းချက်</td>
				<td>Example</td>
			</tr><tr><td><code>String</code></td>
				<td>စကားလုံး/စကားစု</td>
				<td><code>'hello'</code>, <code>"hello world!"</code> etc</td>
			</tr><tr><td><code>Number</code></td>
				<td>နံပါတ်များ</td>
				<td><code>3</code>, <code>3.234</code>, <code> etc.</td>
			</tr><tr><td><code>BigInt</code></td>
				<td>an integer with arbitrary precision</td>
				<td><code>900719925124740999</code> , <code></code> etc.</td>
			</tr><tr><td><code>Boolean</code></td>
				<td>မှန်သည် (သို့) မှားသည် </td>
				<td><code>true</code> and <code>false</code></td>
			</tr><tr><td><code>undefined</code></td>
				<td>မသတ်မှတ်ရသေးသော</td>
				<td><code>let a;</code></td>
			</tr><tr><td><code>null</code></td>
				<td>တန်ဖိုး Null ဖြစ်နေသော</td>
				<td><code>let a = null;</code></td>
			</tr><tr><td><code>Symbol</code></td>
				<td>သင်္ကေတ</td>
				<td><code>let value = Symbol('hello');</code></td>
			</tr><tr><td><code>Object</code></td>
				<td>အချက်အလက်များ စုစည်းထားသော</td>
				<td><code>let student = { };</code></td>
			</tr></tbody></table>

### Note

- `string` data-type သည် -**Single quotes**: `'Hello'` -**Double quotes**: `"Hello"`
  -- **Backticks**: `` `Hello` `` စသည် တို့ တစ်ခုခုဖြင့် ရေးသားပေးရသည်။ Single/Double quotes, backticks မပါသော text သည် `string` မဟုတ်ပေ။ ထို့ပြင် `"6"` `"209"` စသည်တို့သည် Double quotes ဖြင့် ရေးထားသောကြောင့် `Number` data-type မဟုတ်ပဲ `string` data type ဖြစ်သည်။

- အထက်တွင် ဖော်ပြထားသောdata types ထဲတွင် `object` data-type တစ်ခုမှလွဲပြီး ကျန် အားလုံးသည် **Primitive Data Type** (ထပ်ခွဲ၍ မရနိုင်သော) ဖြစ်ပြီး `object` data-type မှာ **Non-Primitive Data Type** (ထပ်ခွဲ၍ ရ) ဖြစ်သည်။

### Variable

Variable ကြေငြာရန် var , let , const စသည့် keyword များ အသုံးပြုပေးရသည်။
**Syntax**
`keyword` `Variable's name` = `Value` ;

    var num1 = 4 ;
    let userName =  "Aung Myanmar" ;
    const age = 30 ;

### note

- **var နှင့် let** သည် တစ်ခါကြေငြာပြီး နောက် **ပြုပြင်ပြောင်းလဲ၍ ရ**ပါသည်။
- **const** ကို အသုံးပြုပြီး ကြေငြာထားရင်ေတာ့ **ထပ်မံပြောင်းလဲ၍ မရနိုင်**ပါ။

`keyword` `Variable's name` = `Value` ; (**console,log result**)

example : 1 ( **var** )

    var userName = "ko ko" ; ( ko ko )
      userName = "Mg Mg" ; ( Mg Mg )

example : 2 ( **let** )

     var num1 = 5
      const num2= 8;
       let num3 = 2 ; ( 2 )
       num3 = num1 + num2 ; ( 13 )

example : 3 ( **const** )

    var num5 = 7 :
    const num6 = 3 ; ( 3 )
    let num7 = 19 ;
    num6 = num5 + num7 ; ( Error )

### Important Note

- Javascript ကကြိုတင်သတ်မှတ်အသုံးပြုထာသည့် keyword များကို
  variable name (or) function name အဖြစ် သုံးစွဲခွင့်မရှိပါ။

##

### Object

Object ဆိုတာ data တွေ valueတွေ အများကြီးပါတဲ့ variable တစ်ခုလိုပါပဲ။

#### Declare Syntax

`const` `object-name` = {
`property-key` : `"property-value"` `,`
`key` : `value`
} ;

![enter image description here](https://miro.medium.com/max/856/0*7EptITWWPaI9BoxL.png)

#### Usage syntax

`object-name`.`key` **(Dot** Notation)
`object-name`[`"key"`] (**Bracket** Notation)

#### example

    const user = {
                  name : "Aung Aung",
                  age : 23,
                  address : "Yangon"
                  }
    //dot notation
    const getUserName = user.name;
    console.log(getUserName);
    //"Aung Aung"

    // bracket notation
     const getUserAge = user["age"];
     console.log(getUserAge);
     //23

### Important Note

- object ထဲမှာ property တစ်ခုထပ်ပိုရင် နောက် object မ‌ရေးခင် ကော်မာ **`,`** ထည့် ပေးရပါမယ်။ <br>
  -Example

        const myObj = {
                        name : "aung aung" ,
                        age : 27
                       }

- object သိမ်းမယ့် **variable ကြေငြာရင်** `let` / `var` အစား **`const`** **ကိုသာ အသုံးပြုသင့်**ပါတယ်။

##

JavaScript Function အကြောင်း လေ့လာသွားကြမှာပါ။၊<br>
`function` တွေကို အချိန် နဲ့ နေရယူတာကို လျော့နည်းစေရန်၊ တူညီတဲ့လုပ်ဆောင်ချက်များကို ထပ်ခါထပ်ခါ ရေးစရာမလိုပဲ တစ်ခါသတ်မှတ်ထားရုံနဲ့ ပြန်လည်ပြီး အကြိမ်ကြိမ် အသုံးပြုနိုင်ရန်၊ စတာတွေအတွက် အသုံးပြုကြပါတယ်
![enter image description here](https://res.cloudinary.com/practicaldev/image/fetch/s--pClJgvrv--/c_limit,f_auto,fl_progressive,q_auto,w_880/https://dev-to-uploads.s3.amazonaws.com/i/mt2jlra7jd5gdgl8up8y.png)

#### JavaScript မှာ function ကို အသုံးပြုမယ်ဆိုရင်

1.  function ကို အရင် သတ်မှတ် ပေးရပါမယ် (define, declare)
2.  ထို သတ်မှတ်ထားတဲ့ function ကို အသုံးပြုရန် / အလုပ်လုပ်စေရန် function ကို ပြန်လည်ခေါ်ယူ ပေးရပါမည်။(call)

##

### Function တစ်ခု သတ်မှတ်ခြင်း (define, declare)

- ပထမနည်းလမ်း
  syntax
  `function-keyword` `functionနာမည်` ( `parameter` ){
  `function body ;`
  } ;

code

```js
function helloWorld() {
  console.log("Hello world");
}
```

- **ES6 arrow Function** (anonymous အမည်မဲ့)
  syntax
  `(parameter)` `=>` `{`
  `function body;`
  `}`

code

```js
() => {
  console.log(" Hello world");
};
```

**ES6** function ကို variable တစ်ခုထဲတွင် သိမ်းထားလေ့ရှိပါတယ်။
code

```js
const sayHello = () => {
  console.log(" Hello ");
};
```

##

### Function ကို ခေါ် ယူအသုံးပြုခြင်း

အထက်မှာ ဖော်ပြခဲ့သလို function တွေကို သတ်မှတ်လိုက်ရုံ နဲ့ ဘာ လုပ်ဆောင်ချက်မျှ
ပြုလုပ်ပေးမည်မဟုတ်ပါ။<br>
သတ်မှတ်ထားတဲ့ **function Name** (or) **သိမ်းထားတဲ့ variable Name** ကို **ခေါ််ပေးမှသာ** function က အလုပ်လုပ်မည်ဖြစ်သည်။

```js
function helloWorld() {
  console.log("Hello world");
}
helloWorld(); //call by function name

//Hello world
```

**ES6**

```js
const sayHello = () => {
  console.log(" Hello ");
};
sayHello(); //call by variable name

// Hello
```

##

### **Function with parameter**

- function name နောက်က လက်သဲကွင်း ထဲမှာ parameter ကို ထည့် သွင်းကာ define လုပ်နိုင်သည်။
- ထို function ကို ခေါ် သုံးသောအခါ နောက်က လက်သဲကွင်း ထဲမှာ parameter ရဲ့ တန်ဖိုးကို ထည့် သွင်း
  ပြီး အသုံးပြုနိုင်ပါသည်။

code

```js
//example - 1

function sayHi(name) {
  console.log("Hi" + " ," + name);
}

sayHi("Mg Mg");
// Hi ,Mg Mg

sayHi("Su Su");
// Hi ,Su Su

example - 2;

function numberPlus(a, b) {
  console.log(a + b);
}
numberPlus(2, 5);
// 7
numberPlus(80, 160);
// 240
```

### ES6

```js
//example - 1

const helloUser = (name) => {
  console.log("Hello" + " ," + name);
};

helloUser("Mg Mg");
// Hello ,Mg Mg

helloUser("Su Su");
// Hi ,Su Su

//example -2

const multipleNumber = (a, b) => {
  console.log(a * b);
};

multipleNumber(2, 5);
// 10

multipleNumber(80, 160);
// 12800
```

##

### Return

- function များ၏ လုပ်ဆောင်ချက်**ရလဒ် များကို ရယူအသုံးပြုနိုင်ရန်** return ဖြင့် ထုတ်ပြန်ပေးရသည်။
  မှတ်ချက်။ ။ **console.log သည်** ရလဒ်ကို အသုံးပြုနိုင်ရန် ထုတ်ပေးခြင်း မဟုတ်ပါ။ <br>
  **console ထဲတွင် log တစ်ခုအနေနဲ့ ပြသပေးရုံသာ** ဖြစ်သည်။

- function များကို **return မပေးထားရင် Undefined** ဟူသော တန်ဖိုး
  ပြန်ထုတ်ပေးသည်။

```js
const toCheck = (a, b) => {
  return a + b;
};
toCheck(3, 4);
//return 7
```

### Try this ....

```js
const cake = 5;
const juice = 3;
const orange = 1;
const apple = 4;
const dragon = 4000;
const discountPrice = 1;
let normalPrice;
let toPay;

const totalPrice = (price1, price2) => {
  normalPrice = price1 + price2;
  return normalPrice;
};
totalPrice(cake, juice);

const haveToPay = (a, b) => {
  toPay = a - b;
  return toPay;
};
haveToPay(normalPrice, discountPrice);

console.log("You Have to Pay " + toPay + "$" + " " + "Total");
```

**totalPrice** function ခေါ််တဲ့အခါ **parameter** တွေမှာ အခြားတန်ဖိုးတွေ ( orange , apple, dragon) အစားထိုးပြီး **console မှာ run** ကြည့်ပါ။

##

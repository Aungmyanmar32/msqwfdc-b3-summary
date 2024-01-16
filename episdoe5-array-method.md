### Built-in method

- javascript မှာ အသင့်လုပ်ပြီးသား method တွေ ပါရှိပါတယ်
- method ဆိုတာကလဲ function ပဲ ဖြစ်တာမလို့ သတ်မှတ်စရာမလိုပဲ တိုက်ရိုက်ခေါ်သုံးလို့ရပါတယ်
- array မှာ သုံးလို့ရမယ့် အသုံးများတဲ့ method တွေကို ပြန်လေ့လာကြည့်ကြပါမယ်
- method တွေကို သုံးတဲ့အခါ ဘာကို return ပြန်ထုတ်ပေးသလဲဆိုတာကို သိထားဖို့က အရေးကြီးပါတယ်

##

### `array.find()` method

- array တစ်ခုထဲရှိ item ( element) တွေထဲက item တစ်ခုကို ရှာချင်တဲ့အခါ သုံးလေ့ရှိပါတယ်
- မူရင်းarray ရှိ item များကို loop လုပ်ကာ **သတ်မှတ်ချက်နှင့်အညီ စစ်ဆေးပြီး မှန်ကန်မှုရှိတဲ့( true) item တစ်ခုကိုသာ ‌**ရွေးချယ်ပြီး ပြန်ထုတ်ပေးသည်။<br>**မူရင်း array ရှိ item များ အားလုံး ပြောင်းလဲခြင်းမရှိပါ**

### syntax

```js
array.find(callback-function)
```

### Example

```js
const users = [
  {
    name: "aung",
    age: 30,
  },
  {
    name: "thura",
    age: 30,
  },
  {
    name: "ezio",
    age: 30,
  },
];

const findInArray = users.find((item) => item.name === "thura");
console.log(findInArray);
//log  { name: "thura", age: 30 }
```

- find method နဲ့ ရှာတဲ့အခါ callback function မှာ စစ်ထားတဲ့ codition က true ထုတ်ပေးတဲ့ item ကို return လုပ်ပေးမှာဖြစ်ပါတယ်
- callback function မှာ စစ်ထားတဲ့ codition က true ထုတ်ပေးတဲ့ item ကို တွေ့ပြီး ဆိုရင် array ထဲရှိ ကျန် item တွေကို loop ထပ်မလုပ်တော့ပဲ ထွက်သွားလိုက်မှာဖြစ်ပါတယ်
- ဆိုလိုတာက find method ကို သုံးလို့ရှိရင် callback မှာ return true ဖြစ်နိုင်တဲ့ item တွေ အများရှိနေပေမယ့် ပထဆုံး true ဖြစ်တဲ့ item ကနေပဲ loop ကို ရပ်နားလိုက်မှာဖြစ်ပါတယ်
- အထက်ပါ users array မှာ age 30 ဖြစ်တဲ့ user ကို ရှာမယ်ဆိုပါစို့
- user အကုန်လုံး က age 30 ဖြစ်တာမလို့ အကုန်လုံးကို return လုပ်ပေးမှာမဟုတ်ပဲ ပထမ item ဖြစ်တဲ့ `{ name: "aung", age: 30 }` ကို သာ return လုပ်ပေးမှာဖြစ်ပါတယ်။

### Example

```js
const users = [
  {
    name: "aung",
    age: 30,
  },
  {
    name: "thura",
    age: 30,
  },
  {
    name: "ezio",
    age: 30,
  },
];

const findInArray2 = users.find((item) => item.age === 30);
console.log(findInArray2);
//log  { name: "aung", age: 30 }
```

- callback function မှာ စစ်ထားတဲ့ codition က true ထုတ်ပေးတဲ့ item မရှိခဲ့ရင်တော့ undefined ကို return ပြန်ပေးမှာဖြစ်ပါတယ်
- ### Example

```js
const users = [
  {
    name: "aung",
    age: 30,
  },
  {
    name: "thura",
    age: 30,
  },
  {
    name: "ezio",
    age: 30,
  },
];

const findInArray2 = users.find((item) => item.name === "okar");
console.log(findInArray2);
//log  undefined
```

### `array.filter()` method

မူရင်းarray ရှိ item များကို loop လုပ်ကာ **သတ်မှတ်ချက်နှင့်အညီ စစ်ဆေးပြီး မှန်ကန်မှုရှိတဲ့( true) item များကိုသာ ‌**ရွေးချယ်ပြီး **array အသစ်တစ်ခု** ပြန်ထုတ်ပေးသည်။<br>**မူရင်း array ရှိ item များ အားလုံး ပြောင်းလဲခြင်းမရှိပါ**

#### syntax

`array`.`filter`(`callback function`);

```js
const arryItem = [
  {
    name: "Aung AUng",
    age: 34,
  },
  {
    name: "Ko Ko",
    age: 24,
  },
  {
    name: "Su Su",
    age: "18",
  },
  {
    name: "Bo Bo",
    age: 23,
  },
  {
    name: "Mg Mg",
    age: 26,
  },
];

const youngPeople = arryItem.filter((user) => {
  return user.age < 25;
  //အသက် ၂၅ အောက်ကိုသာ ‌စစ်ထုတ်ပေးပါ
});

console.log(youngPeople);

// (3) [{…}, {…}, {…}]
// 0: {name: 'Ko Ko', age: 24}
// 1: {name: 'Su Su', age: '18'}
// 2: {name: 'Bo Bo', age: 23}
```

##

### array.map() method

**မူရင်း array ရှိ item များ အားလုံးကို loopလုပ်**ပေးပြီး **array အသစ်တစ်ခု** ထုတ်ပေးသည်။<br>**မူရင်း array ရှိ item များ အားလုံး ပြောင်းလဲခြင်းမရှိပါ**

#### Syntax

`array`.`map`(`callback-function`) ;<br>

`array`.`map`((`parameter`)`=>` `{`
do something
`}`
`)` ;<br>

#### short-hand

`array`.`map`((`parameter`)`=> `do something`) `;<br>

#### Example..1

```js
const itemsArr = [1, 2, 3, 4, 5];
const newArr = itemsArray.map((element) => element + 1);
console.log(newArr);
//output : (5) [2, 3, 4, 5, 6]
//auto return in short-hand syntax
```

#### Example..2

```js
const itemsArr = [1, 2, 3, 4, 5];
const newArr = itemsArr.map((element) => {
  const newItem = element + 1;
  return newItem;
});
console.log(newArr);
//(5) [2, 3, 4, 5, 6]

//if no return
const newArr = itemsArr.map((element) => {
  const newItem = element + 1;
});
console.log(newArr);
//(5) [undefined,undefined,undefined,undefined,undefined]
```

##

အပေါ် က filter method ထဲက လို ၂၅ အောက်တွေကိုပဲ စစ်ထုတ်ပြီး သူတို့ နာမည်ပဲ လိုချင်တယ် ဆိုပါစို့။

```js
const arryItem = [
  {
    name: "Aung AUng",
    age: 34,
  },
  {
    name: "Ko Ko",
    age: 24,
  },
  {
    name: "Su Su",
    age: "18",
  },
  {
    name: "Bo Bo",
    age: 23,
  },
  {
    name: "Mg Mg",
    age: 26,
  },
];

//method 1
//filter people under 25
const youngPeople = arryItem.filter((user) => user.age < 25);

//get name of under 25
const getName = youngPeople.map((people, index) => people.name);
console.log(getName);
//(3) ['Ko Ko', 'Su Su', 'Bo Bo']

//////
//method 2
// အပေါ်ကလို တစ်ခုစီခွဲမရေးပဲ တစ်ခါတည်း တွဲရေးလိုက်လို့လဲရပါတယ်
const getYoungPeopleName = arryItem
  .filter((user) => user.age < 25)
  .map((people) => people.name);
console.log(getYoungPeopleName);
//(3) ['Ko Ko', 'Su Su', 'Bo Bo']
```

`array.map((element, index) => run this);` <br>
`map()` /`filter()` / `find()` method မှာ **callback function** က **parameter နှစ်ခု** လက်ခံလို့ရပြီး<br>**ပထမ parameter** က **element** ကို ခေါ် မှာ ဖြစ်ပြီး <br>**ဒုတိယ parameter**က ထို **element ရဲ့ index** တန်ဖိုး ဖြစ်ပါတယ်။ <br>နမူနာ ပြထားတဲ့ code မှာတော့ <br>`youngPeople.map((people,index) =>people.name);` <br>index ကို parameter အဖြစ်သာ ထည့်ထားပြီး callback function မှာ ဘာလုပ်ဆောင်ချက်မှ မပေးထားပါဘူး။<br>
ဒီလိုလေး စမ်းကြည့်ပါ

```js
const getName = youngPeople.map((people, index) => index + " " + people.name);
console.log(getName);
//output : (3) ['0 Ko Ko', '1 Su Su', '2 Bo Bo']
```

**index နေရာမှာ တခြားစာလုံးဖြစ်လဲ index တန်ဖိုးကိုပဲ ထုတ်ပေးမှာပါ**

```js
const getname2 = youngPeople.map(
  (people, spiderMan) => spiderMan + " " + people.name
);
console.log(getName2);
//output : (3) ['0 Ko Ko', '1 Su Su', '2 Bo Bo']
```

##

### array.reduce()

- array ထဲရှိ item တွေကို ချုပ်လိုက်ပြီး တန်ဖိုးတစ်ခုကို return လုပ်ပေးသည်

### syntax

```js
array_name.reduce( callback_function, initialValue )

array_name.reduce( (accumulator, currentValue)=>{...}, initialValue )

//example

const stocks = [
    {name:"shirt", price: 300},
    {name:"tv", price: 5000},
    {name:"chair", price: 1500},
]

//find total price for all stock
let totalPrice = stocks.reduce((acc, cur) => {
    return acc + cur.price;
}, 0);

console.log(totalPrice);

// Find the stock with the highest price ??


```

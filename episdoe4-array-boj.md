### Object

Object ဆိုတာ data တွေ valueတွေ အများကြီးပါတဲ့ variable တစ်ခုလိုပါပဲ။

#### Syntax

`const` `object-name` = {
`property-key` : `"property-value"` `,`
`key` : `value`
} ;

![enter image description here](https://miro.medium.com/max/856/0*7EptITWWPaI9BoxL.png)

#### Usage syntax

`object-name`.`key` **(Dot** Notation)
`object-name`[`"key"`] (**Bracket** Notation)

#### example

```js
const user = {
  name: "Aung Aung",
  age: 23,
  address: "Yangon",
};
//dot notation
const getUserName = user.name;
console.log(getUserName);
//"Aung Aung"

// bracket notation
const getUserAge = user["age"];
console.log(getUserAge);
//23
```

### Important Note

- object ထဲမှာ property တစ်ခုထပ်ပိုရင် နောက် object မ‌ရေးခင် ကော်မာ **`,`** ထည့် ပေးရပါမယ်။ <br>
  -Example

```js
const myObj = {
  name: "aung aung",
  age: 27,
};
```

- object သိမ်းမယ့် **variable ကြေငြာရင်** `let` / `var` အစား **`const`** **ကိုသာ အသုံးပြုသင့်**ပါတယ်။

##

### Array

object ကဲ့သို့ data တွေ valueတွေ အများကြီးပါတဲ့ variable တစ်ခုလိုပါပဲ<br>

#### Declare Syntax

`const` `array-name` = `['A','B','C','D','E','F' `] ;

ခေါ် တဲ့အခါကျရင် object မှာကဲ့သို့ (**Dot** Notation) (**Bracket** Notation) တွေ မသုံးပဲ index နဲ့ အသုံးပြုရမှာပါ။

### Index သတ်မှတ်နည်း

![enter image description here](https://miro.medium.com/max/640/1*hLp5vDQse-YUOpvgI9hfDw.webp)

#### Usage syntax

‌`array-name`[`index`];

#### example

```js
const myLetter = ["A", "B", "C", "D", "E", "F"];
const getLetter = myLetter[0];
console.log(getLetter);
//'A'
const getLetter2 = myLetter[4];
console.log(getLetter2);
//'E'
```

### Important Note

- **Array ** မှာ ရှိတဲ့ items တွေ ဘယ်လောက်ပါလဲ သိချင်ရင် **`.length`** ကို သုံးပါတယ်။
  - **`index` ကို** စရေရင် **0** နဲ့ စပြီး , **`length` ကို 1** နဲ့ စပါတယ်။
  - array တစ်ခုရဲ့ **နောက်ဆုံး`index`** ကို လိုချင်ရင် **‌array.length -1** နဲ့ ရယူနိုင်ပါတယ်။

###

```js
const myLetter = ["A", "B", "C", "D", "E", "F"];
//   index       0   1   2   3   4   5
//   length      1   2   3   4   5   6
const getLength = myLetter.length;
const lastIndex = myLetter.length - 1;
console.log(getLength);
console.log(lastIndex);
//6
//5
```

##

### Object in Array

#### syntax

```js
const myUser = [
  "Bo Bo",
  {
    name: "ko ko",
    age: 35,
  },
  "27",
];
```

```js
// to get ko ko and his age
const userName = myUser[1].name;
const userAge = myUser[1].age;
console.log(userName + " is " + userAge + " years old");
// ko ko is 35 years old

//get Bo Bo and his age
const userName2 = myUser[0];
const userAge2 = myUser[2];
console.log(userName2 + " is " + userAge2 + " years old");
// Bo Bo is 27 years old
```

##

    ### Callback function

Function တစ်ခုထဲ နောက် function တစ်ခုကို parameter အဖြစ် ထည့်ပေးလိုက်ရင် ထို အထည့်ခံ function ကို callback function လို့ ခေါ် ပါတယ်။<br>
**ပထမ function အလုပ်လုပ်ပြီးမှ နောက် functionတစ်ခုကို အလုပ်ခိုင်းချင်တဲ့အခါ callback အနေနဲ့ သုံးလေ့ရှိပါတယ်။**

#### Example..1

```js
const functionOne = (parameter) => {
  console.log("I am not callback");
  parameter();
};

const functionTwo = () => {
  console.log("I am callback");
};
functionOne(functionTwo);
//functionOneအရင်လုပ်ပါ(functionOneပြီးမှ functionTwoနောက်ကလုပ်ပါ=callback)

//output 1: I am not callback
//output 2: I am callback
```

#### Example..2

```js
const functionOne = (parameter) => {
  console.log("I am not callback");
  parameter(1, 2);
};
const functionTwo = (a, b) => {
  console.log(a + b);
};
functionOne(functionTwo);
//output 1: "I am not callback"
//output 2: 3
```

##

- **callback function ခေါ်** တဲ့ အခါ သိမ်းထားတဲ့ **variable name ကိုသာ ရေး**ပေးရမည်။<br>
  `functionOne(functionTwo)` **YES**<br>
  ~~`functionOne(functionTwo())`~~ **NO**

##

CLI (**C**ommand **L**ine **I**nterface)<br>
အကြောင်း လေ့လာသွားမှာပါ။

> **interface**
<br/>
> အရာ တစ်ခု ကနေ နောက်အရာတစ်ခုကို ပေါင်းကူး ဆက်သွယ်ပေးတဲ့ ကြားခံအရာတစ်ခု ဖြစ်ပါတယ်။

### GUI ( Graphical User Interface)

ထိတွေ့ကိုင်တွယ်လို့ ရသော Interface ။<br>

> တစ်နည်း

User များ အသုံးပြုရ လွယ်ကူစေရန် ပြုလုပ်ပေးထားသော Interface<br>
![enter image description here](https://study.com/cimages/videopreview/videopreview-full/what-is-a-graphical-user-interface-gui-definition-components-examples_117052.jpg)

##

### TUI (Text User Interface)

Text/command တွေနဲ့သာ အသုံးပြုနိုင်အောင် ပြုလုပ်ပေးထားသော interface<br>
![enter image description here](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Linux_command-line._Bash._GNOME_Terminal._screenshot.png/800px-Linux_command-line._Bash._GNOME_Terminal._screenshot.png)

##

### CLI (**C**ommand **L**ine **I**nterface)

Computer ရှိ Command Prompt/terminal မှ တစ်ဆင့် Command line များအသုံးပြုပြီး <br>
file,folder စတာတွေကို ထိန်းချုပ်ဖန်တီးသည့် နည်းပညာဖြစ်သည်။<br>
file,folder စတာတွေကို Command Prompt/terminal မှ <br>တစ်ဆင့် အောက်ပါ Command lineများ ရေးထည့်ပေးခြင်းဖြင့် <br>အလွယ်တကူ လျင်လျင်မြန်မြန် ထိန်းချုပ်ဖန်တီးနိုင်သည်။

##

### Useful Commands for CLI

| command     | usage                     | meaning                                                   |
| ----------- | ------------------------- | --------------------------------------------------------- |
| pwd         | `pwd`                     | လက်ရှိရောက်နေသော နေရာ working **dir(Directory)**          |
| ls          | `ls`                      | လက်ရှိရောက်နေသော နေရာ ရှိ ဖိုင်များစာရင်း                 |
| cd          | cd dir-name               | dir သို့ သွားပါ                                           |
| `*example*` | `cd Desktop/`           | (go to Desktop)                                           |
| `cd ..`     | `cd ..`                 | လက်ရှိရောက်နေသော နေရာမှ **နောက်သို့ တစ်ဆင့်** ပြန်ထွက်ပါ။ |
| touch       | touch file-name           | ဖိုင် အသစ်လုပ်ပါ                                          |
| `*example*` | `touch test.txt`        | test.txt ဖိုင်တစ်ခု လုပ်သည်။                              |
| rm          | rm file-name              | ဖိုင်ဖျက်သည်။                                             |
| `*example*` | `rm test.txt`           | test.txt ဖိုင်ကို ဖျက်ပစ်သည်။                             |
| mkdir       | mkdir folder-name         | folder/dir တစ်ခု လုပ်သည်။                                 |
| `*example*` | `mkdir my-folder`       | my-folder dir တစ်ခု လုပ်သည်။                              |
| rm -r       | rm -r dir-name            | folder/dir ကို ဖျက်သည်။                                   |
| `*example*` | `rm -r my-folder`     | my-folder dir ကို ဖျက်ပစ်သည်။                             |
| open        | open file-name            | file ကို ဖွင့်သည်။                                        |
| `*example*` | `open test.txt`         | test.txt file ကို ဖွင့်သည်။                               |
| mv          | mv old-name new-name      | file ကို အမည်ပြောင်းသည်။                                  |
| `*example*` | `mv test.txt new.txt` | test.txt file ကို new.txt သို့ အမည်ပြောင်းသည်။            |
| mv          | mv file-name dir-name     | file ကို နေရာ ပြောင်းသည်။                                 |
| `*example*` | `mv new.txt Desktop/` | new.txt file ကို Desktop dir သို့ ပြောင်းသည်။             |
| cp          | cp file-name dir-name     | file ကို ကူးယူသည်။`**(Copy)**`                            |
| `*example*` | `cp new.txt Desktop/` | new.txt file ကို copy ကူး ပြီး Desktop dirသို့ ထည့်သည်။   |
| clear       | `clear`                   | terminal ရှိ code များ ရှင်းလင်းပေးသည်။                   |

##

##

## Typescript

- Typescript ဆိုတာ javascript superset တစ်မျိုးဖြစ်ပါတယ်။
- Typescript သည် စောစောစီးစီး အမှားထောက်လှမ်းခြင်း နှင့်ခိုင်မာသောTyping တို့အပါအဝင် runtime အမှားများကို ရှာဖွေရန် အသုံး၀င်သည်။
-

##

### Install Typescript in Project

- terminal ထဲ `npm i g typescript` လို့ ရေးပြီး typescript ကို install လုပ်ပေးပါ။
- Typescript ဖိုင် များသည် `.ts` ဖြင့် file extension သတ်မှတ်ပေးရပါသည်( eg: script.ts )
- Typescript ဖြင့် ရေးသားထားသော ဖိုင်များကို မူလ language file အဖြစ် သို့ ပြန်ပြောင်းပေးရပါတယ် ( ဥပမာ ။ ။ javascript ကို typescript ဖြင့်ရေးထားပြီး `.ts` extension နဲ့ သိမ်းထားတာကို **typescript မှ javascript** `.js` ဖိုင် အဖြစ်သို့ **tsc ကို သုံးပြီး** ပြန်ပြောင်းပေးရမှာပါ )
-

## Typescript Data type

- နောက်ပိုင်း သင်ခန်းစာမှာ typescript ကို ( ts ) လို့ပဲ သုံးသွားပါမယ်
- ts မှာ variable ကြေငြာရင် data-type သတ်မှတ်ပေးရပါတယ်။
- script.ts ဖိုင် တစ်ခုလုပ်ပါမယ်
- ဖိုင်ထဲမှာ variable တွေ လုပ်ကြည့်ပါမယ်

```ts
const num1: number = 20;

const userName: string = "aung aung";

const isOk: boolean = true;
```

- num1 ရဲ့ တန်ဖိုး က number ဖြစ်ကြောင်း သတ်မှတ်ထားလိုက်တာဖြစ်ပါတယ်
- ခုလို သတ်မှတ်လိုက်တာနဲ့ num1 တန်ဖိုးက number data type မှ လွဲပြီး ကျန် string တို့ undefended တို့ ဖြစ်လာရင် error ပြပေးမှာဖြစ်ပါတယ်။
- သတ်မှတ်ထားတဲ့ data type နဲ့ variable တန်ဖိုးတို့ type တူမှသာ
  error ပျောက်သွားမှာဖြစ်ပါတယ်။
- ကျန်တဲ့ userName / isOk တွေလည်း ထိုနည်းအတိုင်းပါပဲ။

##

### Typescript complier ( tsc )

- Typescript ဖြင့် ရေးသားထားသော ဖိုင်များကို မူလ language file အဖြစ် သို့ ပြန်ပြောင်းပေးရပါတယ် ( ဥပမာ ။ ။ javascript ကို typescript ဖြင့်ရေးထားပြီး `.ts` extension နဲ့ သိမ်းထားတာကို **typescript မှ javascript** `.js` ဖိုင် အဖြစ်သို့ **tsc ကို သုံးပြီး** ပြန်ပြောင်းပေးရမှာပါ )

```properties
tsc script.ts
```

- ဒီ command က **script.ts** ဖိုင် ဖတ်ပြီးကို **typescript ကို javascript အဖြစ် ပြန်ပြောင်း**ကာ **script.js ဖိုင်တစ်ခု create လုပ်**ပေးလိုက်ပါတယ်
- vs code explorer ထဲမှာ script.js ဖိုင်တစ်ခုတိုးလာတာမြင်ရမှာပါ။

##

### function

- ts မှာ function သတ်မှတ်တဲ့ အခါ parameter နောက်မှာ return ပြန်မယ့် data type ကို သတ်မှတ်ပေးရပါမယ်
- function မှာ လဲ return တစ်ခု ပြန်ပေးရပါမယ်

```ts
const num1: number = 20;
const userName: string = "aung aung";
const isOk: boolean = true;

const testFunction = (): number => {
  return num1;
};
```

---

### Function with parameter

```ts
const testFunction = (num2: number, num3: number): number => {
  return num2 * num3;
};

testFunction(2, 12);
```

- function ထဲမှာ parameter လက်ခံရင် အဆိုပါ parameter ကိုပါ data type သတ်မှတ်ပေးရပါတယ်။

##

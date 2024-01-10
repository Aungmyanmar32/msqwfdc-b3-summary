## MSquare Programming Fullsatck Developer Course ( Batch 3)

### Episode 1 Summary

##

Episode 1 မှာတော့

- Html အကြောင်း
- Html Tag အကြောင်:
- Html Tag တွေရဲ့ Attribute အကြောင်း
- CSS အကြောင်း
  စတာတွေ လေ့လာသွားပါတယ်။

### Html

Html အကြောင်းမှာတော့
web တွေ စတင်တုန်းက Html သီးသန့် ပဲ သုံးခဲ့ကြကြောင်း၊
စာဖတ်ဖို့ သက်သက်သာ သုံးခဲ့ကြကြောင်း၊
CSS,JS တွေ နောက်ပိုင်းမှ ပေါ်လာတာ ဖြစ်ပါတယ်။
သဘောပြောရရင်
Html က Naked ဖြစ်နေတဲ့ လူတစ်ယောက်ဆိုပါစို့
CSS က အ၀တ်အစားဆင် မိတ်ကပ်ပြင်ပေးလိုက်တာပါ။
JS က လှုပ်ရှားမှု(action)တွေ ထည့်ပေးလိုက်တာပါ။
Html fileတွေကို chrome/firefox စတဲ့ web browser တွေမှာ ဖွင့်ကြည့်လို့ ရပါတယ်။

### Html Document structure

![enter image description here](https://lecturely.com/assets/ckeditor/imageuploader/uploads/html-cheatsheet-intro.png)

- **_!DOCTYPE html_** ဆိုတာက Html file ဖြစ်ကြောင်း browser ကို ပြောလိုက်တာပါ။
- html document တစ်ခုကို Html file ဖြစ်ကြောင်း ကြေငြာပြီးရင်
- html ဖိုင်ကို **_.html_** နဲ့ file format ထားသိမ်းပေးရပါမယ်.
- `<html> ` နဲ့ စပြီး `</html>`နဲ့ ပိတ်ပေးရပါမယ်။

### **Html tag**

- Html tag ရေးရင် **အဖွင့် tag** `<body> ` နဲ့ **အပိတ် tag** `</body> ` ရေးပေးရပါတယ်။
- ကိုယ်ပြချင်တဲ့ အကြောင်းအရာကို `<body> ` နဲ့ `</body> `ကြားမှာ ရေးပေးရပါမယ်။

### ထူးခြားပြီး အသုံးများသောTag အချို့

`<a> `<br>

- Document တစ်ခုကနေ နောက် documentတစ်ခုကို link လုပ်ပေး။
- State less ဖြစ်။
- မူလ document ကနေ နောက် documnetတစ်ခုရောက်ရင် မူလကဟာတွေအကုန်ပျောက်သွားပါတယ်။
  `<a>` tag ကိုဒီလိုရေးလေ့ရှိပါတယ်။<br>
  `<a href="your-link">Google</a>`
  _your-link_ မှာ ကိုယ်သွားချင်တဲ့ url/file ကိုထည့်ပေးရပါတယ်။

##

`<div> `<br>
တကယ်ကို အသုံးများတဲ့ tag ပါ။
အကန့်ကန့် အပိုင်းခွဲပေးတာပါ။

##

`<img> `<br>
ပုံများဖော်ပြချင်တဲ့အခါသုံး။
Img tag အတွက် အပိတ် tag ထည့်ပေးရန်မလို **self-closing**။
ရေးနည်း `<img src="Url" />`
**Url** မှာ ကိုယ်ပြချင်တဲ့ ပုံရဲ့ တည်နေရာ or Link ကိုထည့်ပေးရပါမယ်။
ကိုယ့် ကွန်ပြူတာထဲက ပုံရဲ့ တည်နေရာကို
**relative url** လို့ခေါ်ပြီး အင်တာနက်က ပုံရဲ့ တိုက်ရိုက် link ကို **absolute url** လို့ခေါ်ပါတယ်။

##

`<p> `<br>
စာပိုဒ်ခွဲတဲ့အခါ အသုံးပြုပါတယ်။

##

`<h> `<br>
စာတွေကို ခေါင်းစဥ် အဖြစ် ရေးချင်ရင်သုံးပါတယ်။
`<h1>Header1</h1>`

# Header1

`<h2>Header2</h2>`

## Header2

`<h2>Header3</h2>`

### Header3

`<h3>Heade41</h3>`

#### Header4

`<h5>Header5</h5>`

##### Header5

`<h6>Header6</h6>`

###### Header6

##

## Html Attribute

![enter image description here](https://clearlydecoded.com/assets/images/posts/2017-09-04-anatomy-of-html-tag/html-tag-attributes.png)

**Attribute** ဆိုတာ Html Tag တစ်ခုကို အထူးပြုပေးလိုက်တာပါ
**Attribute** တွေမှာ **Name** နဲ့ **Value** ရှိပြီး အလယ်မှာ **_=_** ထည့်ပေးရပါမယ်။
အသုံးများတဲ့ **Attribute** တွေက
**class / id / src / style** စတာတွေပါပါတယ်။
ထူးခြားချက် အနေနဲ့ **style Attribute** က \***\*html tag** တိုင်းမှာ သုံးလို့ရပါတယ်\*\*

##

## important Note

- Html tag(Element) တွေမှာ
  **Inline level Element** နဲ့ **Block level Element**ရှိပါတယ်။
  **Inline level element** ဟာ သူ့ရဲ့ ရှိသလောက် width ပမာဏသာ နေရာယူပြီး ကျန်နေသေးတဲ့ width ကို နောက် Element ကို နေရာထပ်ပေးပါတယ်။
  **Block level element** ဟာ width အပြည့်နေရာယူလိုက်ပြီး နောက် Element ကို လိုင်း အသစ်မှာ နေရာပေးလိုက်ပါတယ်။

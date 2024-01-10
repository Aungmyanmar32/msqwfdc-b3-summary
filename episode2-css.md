## CSS

![enter image description here](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTP6rtBCZj2zcGdG8zPKtO82omPNVdjqJLbwWk_BMPL6dxD9DAQSMw_5Cjsiuz1B3So9N0&usqp=CAU)

## **CSS**ဆိုတာ Html Element တွေကို style,design,color,layout ပြုပြင်ဖန်တီးလုပ်ဆောင်ပေးတာပါ။

1.  **Inline CSS**
2.  **Internal CSS**
3.  **External CSS**
    ဆိုပြီး သုံးမျိုးရှိပါတယ်။

##

## 1.Inline CSS

Html tag ထဲမှာ style attribute နဲ့ တစ်ခါထဲ ထည့်ရေးတာပါ။
![enter image description here](https://www.myprograming.com/wp-content/uploads/2021/03/inline-CSS.png)
![enter image description here](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQR-adFhG28vCnoBkyiw8YYqdb616ZOsuF7Gw&usqp=CAU)

## 2.Internal CSS

![enter image description here](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSPtBAkGzLManMm4YkOtzSDSL7mD8-iS48SWA&usqp=CAU)

```html
<html>
  <head>
    <style>
      /* tag selector */
      p {
        color(property): red (value);
      }

      /* class selector */
      .hello {
        font-size: 20px;
        color: blue;
      }

      /* id selector */
      #hello {
        border: 1px solid black;
        backgroud-color: #234;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <p>Hello</p>

    <div class="hello">Hello Class</div>

    <div id="hello">Hello ID</div>
  </body>
</html>
```

## 3.External CSS

အပြင်မှာ **style.css** ဖိုင် သက်သက်ရေးပြီး **Html document ထဲ link ချိတ်** အသုံးပြုတာ ပါ။
သူ့ကိုလဲ internal css ကဲ့သို့ပဲ `<head></head>`ကြားမှာ link လုပ်ပေးရပါတယ်။

    <html>

     <head>
      <link rel="stylesheet" type="text/css" href="style.css">
     </head>

     <body>
     </body>

    </html>

##

## Important Note

- CSS မှာ property တစ်ခုထပ် ပိုရင် **;** (semi column) ခံပေးရပါမယ်။
- tag တွေကို နာမည်အတိုင်း ခေါ်သုံးနိုင်
  div tag ကို select(ခေါ်သုံး ) မယ်ဆိုရင် html documentထဲက ရှိရှိသမျှ div tag တိုင်း သက်ရောက်မှု ရှိပါမယ်။
- **class** attribute ကို select(ခေါ်သုံး ) မယ်ဆိုရင် **.** (dot) ရှေ့မှာ ထည့်ပေးရပါမယ်။
- **id** attribute ကို select(ခေါ်သုံး ) မယ်ဆိုရင် **#** (sharp) ရှေ့မှာ ထည့်ပေးရပါမယ်။
- **id** attribute က တစ်ခုကို တစ်ခါပဲ သုံးသင့်ပါတယ်။
  ဆိုလိုတာက `id="koko"` လို့ သုံးပြီးရင် နောက်ထပ် koko ဆိုတဲ့ id ထပ်မသုံးသင့်ပါ။

- လက်တွေ့မှာ \***\*Inline CSS** နဲ့ **Internal CSS ကို အသုံးမပြုကြပဲ** **External CSS** ကို သာ သုံးကြပါတယ်။\*\*
- CSS **precedence** ဦးစားပေးစနစ်
  - တူညီတဲ့ selector တစ်ခုကို ရေးနည်းသုံးနည်းစလုံးမှာproperty တူတူ ကြေငြာထားရင်
  - **Inline CSS** က ဦးစားပေး **နံပါတ် တစ်**
  - **Internal CSS** က ဦးစားပေး **နံပါတ် နှစ်**
  - **External CSS** က ဦးစားပေး **နံပါတ် သုံ**းပါ
  - p tag တစ်ခုကို **inline css** မှာ **red** , **Internal css** မှာ **blue** , **external css** မှာ **yellow** လို့ ကြေငြာထားမယ်ဆိုရင် **precedence** ဦးစားပေးစနစ်အရ **red** ကိုပဲ ပြပေးမှာပါ။
  - ##

### CSS Flex-Box

Html element တွေကို Layoutချတဲ့ အခါ အသုံးပြုပါတယ်။
Real world web app တွေ ရေးတဲ့အခါ တကယ်ကို အသုံများတဲ့ CSS နည်းပညာပါ။
Flex-box ကို မလေ့လာခင် Html Element တွေ ရဲ့ nesting သဘောသဘာ၀ကို အရင်သိထားရပါမယ်။

```html
<div class="container">
  <!-- parent element -->
  <div>child element Div 1</div>
  <div>
    <!-- child element -->
    Div2
  </div>
</div>
```

Div နှစ်ခု ကို Div တစ်ခုထဲမှာ ထည့်ထားပါတယ်။
Div နှစ်ခုကို ထိန်းထားတဲ့ container ဆိုတဲ့ Div ဟာ သူ့အထဲက Div နှစ်ခုရဲ့ မိဘ parent ဖြစ်ပါတယ်။
အထဲက Div နှစ်ခုဟာ container Div ရဲ့ ကလေး child ဖြစ်ကြပါတယ်။

parent Div ကို display : flex; လို့ CSS property ပေးလိုက်တာနဲ့ သူ့ရဲ့ child Div တွေကို နေရာချ စီမံလို့ ရပါပြီး။

```html
<div class="container">
  <!-- parent element -->
  <div>
    <!-- child element -->
    Div 1
  </div>
  <div>
    <!-- child element -->
    Div2
  </div>
</div>

CSS .container { display: flex ; }
```

အသုံးများသော Flex -box property များ

    flex-direction : ### ;
    justify-content : ### ;
    align-items : ### ;
    flex-warp : ### ;

![enter image description here](https://byteiota.com/wp-content/uploads/2020/11/flex-direction.png)
![enter image description here](https://miro.medium.com/max/434/1*iigDGiNFBOUVJQ_07C1B2g.png)
![enter image description here](data:image/png;base64,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)

![enter image description here](https://samanthaming.gumlet.io/flexbox30/10-flex-wrap.jpg.gz)

##

```css
justify-content: center;
align-items: conter;
```

![enter image description here](https://2.bp.blogspot.com/-wSizB5Yw-EU/UCzPr_RVTzI/AAAAAAAAElg/a2BecXgMjSI/s1600/flexbox_layout.png)

### Important Note

- margin /padding စတဲ့ CSS properties တွေဟာ Element တစ်ခုကို နေရာချ တဲ့ အခါ အသုံးပြုပြီး Layout များ လုပ်တဲ့အခါမှာတော့ flex-box ကို အသုံးပြုဖို့ ပိုပြီးသင့်တော်ပါတယ်။
- display inline ဖြစ်တဲ့ element တွေကို width and height ပေးချင်ရင် display : inline-block ဒါမှမဟုတ် display: block; အရင်ပြောင်းပေးရပါမယ်။
- -child DIv တွေကို စီမံချင်ရင် သူတို့တွေကို ထိန်းထားတဲ့ parent Div မှာ display : flex ; ပေးပြီး flex-box properties တွေကို parent Div ရဲ့ CSS အထဲမှာပဲ စီမံရပါမယ်။
- ပုံ နဲ့ စာ ကို center ကျကျ ထားချင်ရင် `vertical-align : middle ;` ကို သုံးနိုင်ပါတယ်။

##

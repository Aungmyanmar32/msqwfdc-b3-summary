### GitHub

GitHub ဆို အလွယ်ဆုံးပြောရရင် Computer ထဲ သိမ်းထားတဲ့ git repo(folder)တွေကို အင်တာနက်(cloud)ပေါ်မှာ သိမ်းထားလို့ရတဲ့ နေရာ(website)တစ်ခုပါ။<br>
GitHub နဲ့ မိမိ ကွန်ပြူတာ ကို လုံလုံခြုံခြုံ ချိတ်ဆက်နိုင်ဖို့ အတွက် SSH (**Secure Shell**) နည်းပညာနဲ့
ချိတ်ဆက်ပေးရပါမယ်။

##

### SSH ဖြင့် ချိတ်ဆက်နည်း

#### (၁) git repo တစ်ခု တည်ဆောက်ခြင်း

[GitHub](https://github.com/) မှာ အကောင့်တစ်ခု ဖွင့်ထားပါ။
<br> create repository ကို နှိပ်ပြီး repo တစ်ခု ဆောက်ပါမယ်။ <br> <br>
![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github11.jpg?raw=true)

- repository name မှာ msquarefdc လို့ပေးပါ။
- အောက်က public and private မှာ private ကို ရွေးပြီး create လုပ်ပါ။
  <br><br>

#### ( ၂ ) SSH key ရယူခြင်း

SSH key ရယူရန်အတွက် အောက်က link ကိုသွားပါ။<br> <br>

![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github1.jpg?raw=true)
`ssh-keygen -t ed25519 -C "your_email@example.com"` ကို copy ကူးယူပါ။
<br>

- ကွန်ပြူတာထဲ က Documents အောက်မှာ projects folder တစ်ခု ဆောက်ပြီး vs code မှာ
  Open folder နဲ့ ဖွင့်ထားပေးပါ။

- New Terminal ဖွင့်ပြီး bash ကို ရွေးထားပေးပါ။
- Terminal ထဲ ခုနက copy ယူထားတဲ့ ဟာကို pasteလုပ်ပါ။
- "your_email@example.com" နေရာမှာ ကိုယ့်ရဲ့ github acc mailကို ထည့်ပေးပါ။<br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github2.jpg?raw=true)

<br> <br>

- Enter ကို သာ အောက်ကပုံလို မပေါ်မချင်း နှိပ်သွားပေးပါ။<br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github5.jpg?raw=true)
  <br>
- `eval "$(ssh-agent -s)"` ရိုက်ထည့်ပြီး enter ခေါက်ပါ။ (Agent pid..) ပြပေးမည်။
- `ssh-add ~/.ssh/id_ed25519` ထပ်ရိုက် enter ခေါက်ပါ။
  Identity added ..... ဆိုပြီး ပြပေးပါမည်။<br><br>

![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github6.jpg?raw=true)

<br><br>
-Identity added နောက်က စာကြောင်းသည် SSH key ၏ တည်နေရာဖြစ်သည်။

- SSH key ကို သွားယူရန်အတွက် file explorer ကနေ မိမိ terminal မှာ ပြထားတဲ့နေရာကို (**ကျနော့မှာတော့ c > Users > Admin > .ssh** ) ကိုသွားရပါမည်။
- id_ed25519.pub ဖိုင်ကို notepad ဖြင့်ဖွင့်ပြီး အထဲက key တွေအကုန်ကူးယူပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github4.jpg?raw=true)
  <br><br>
- GitHub မှာ profiel > setting ကို ၀င်ပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github7.jpg?raw=true)
  <br><br>
- SSH and GPG key ကို ထပ်သွားပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github8.jpg?raw=true)
  <br><br>
- New SSH Key ကို နှိပ်ပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github9.jpg?raw=true)
  <br><br>
- Title မှာ windows11 ရေး ၊ key မှာ ခုနက copy ယူထားတဲ့ key ထည့်ပေးပြီး Add SSH key နှိပ်ပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github10.jpg?raw=true)

##

### clone git repo

- GitHub ကို သွားပြီး msquarefdc repo ထဲ ၀င်ပါ။
- SSH ကို ရွေးပြီး link ကို copy ယူပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github12.jpg?raw=true)
  <br><br>
- vs code ထဲသို့ ပြန်၀င်ပြီး terminal မှာ
  git clone ရေး space ခြားပြီး copy ယူထားတဲ့ link ကို ထည့်ကာ enter ခေါက်ပါ။ yes no မေးလာရင် yes ထည့်ပြီး enter ထပ်ခေါက်ပါ။
  <br><br>
  ![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/git13.jpg?raw=true)
  <br>
- You appear to have cloned an empty repo...လို့ ပေါ်လာရင် clone လုပ်ခြင်း ပြီးပါပြီး။

##

### Github ပေါ်တွင် သိမ်းဆည်းခြင်း

vs code မှာ projects folder အောက်က msquarefdc folder ထဲမှာ index.html ဖိုင်တစ်ခု create လုပ်ကြည့်ပြီး git commit လုပ်ပါမယ်။
<br><br>
![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/git14.jpg?raw=true)
<br><br>
Commitလုပ်ပြီးပြီးဆိုရင် git push နဲ့ GitHub ပေါ် တင်လိုက်ပါ။
<br><br>
![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/github15.jpg?raw=true)
<br><br>
မိမိရဲ့ GitHub repo မှာ refresh လုပ်ကြည့်လိုက်ရင် index.html (started project) ဆိုပြီး ဖိုင်ကို တင်ပြီးဖြစ်တာကို ပြပေးနေမှာပါ။<br><br>
![enter image description here](https://github.com/Aungtat/MSquareFullstackCourseSummary/blob/main/githubf.jpg?raw=true)

##

> Important Note!

- GitHub repository နာမည်ပေးရင် **စာလုံးအသေး နဲ့ space မပါ**ပဲ ပေးလေ့ရှိကြပါတယ်။
- ကွန်ပြူတာထဲရှိ .ssh folder ထဲက file တွေကို ပြင်ဆင်ခြင်း၊ ဖျက်ပစ်ခြင်း များ မလုပ်သင့်ပါ။
  <br>ဆရာ့ စကားအရဆို **လုံး၀ သွား မကလိ မိပါစေနဲ့**။

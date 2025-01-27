
نام پروژه : تانل UDP2RAW + FEC[UDPSPEED] برای وایرگارد

<div align="right">
    <img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/project-management.png" alt="Video Title" width="100">
  </a>
</div>
  </details>
</div>

---------------------------------------------------------------

**امکانات**

<div align="right">
    <img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/ability.png" alt="Video Title" width="100">
  </a>
</div>
  </details>
</div>




- پشتیبانی از UDP
- پایین اوردن PACKET LOST در کانکشن نهایی
- قابلیت تانل بر روی تک پورت و چندین پورت
- امکان استفاده از ایپی 4 و 6
- استفاده از FEC در تانل
- امکان استفاده از IP6IP6 و تانل UDP2RAW به همراه FEC
- امکان استفاده ار ICMP با پرایوت ایپی 4 و تانل UDP2RAW به همراه FEC
- ایجاد سرویس برای تمامی گزینه ها
- امکان حذف تمامی تانل ها و سرویس ها

-------------------

What is FEC ?
FEC stands for Forward Error Correction. It is a technique used in data communication to enhance the reliability of data transmission over unreliable or noisy channels. The purpose of FEC is to detect and correct errors that may occur during transmission without the need for retransmission.
Overall, FEC helps improve the reliability and quality of data transmission by adding error correction codes to the transmitted data, allowing for the detection and correction of errors at the receiving end.

 ------------------------------------------------------

 <div align="right">
  <details>
    <summary><strong>توضیحات</strong></summary>
  
------------------------------------ 

- حتما در سرور تست، نخست تانل را ازمایش کنید و سپس اقدام به استفاده از آن بکنید.
- این احتمال هست که بر روی بعضی سرور های ایران کار نکند.
- باید توجه داشته باشید برای تمرین و اموزش خودم، اقدام به ساخت اسکریپت میکنم و در کنارش آموزش هم مینویسم که شما اگر خواستید استفاده کنید.
- در این اسکریپت از منوی جدیدی استفاده کردم. میتوانید با کیبورد، گزینه مورد نظر را انتخاب کنید و سپس ENTER بزنید.
- در این تانل شما میتوانید از ICMP[IPV4] و IP6IP6 و FEC و بدون FEC استفاده کنید.
- هیچ پورت دیفالتی در این تانل گذاشته نشده است.
- پنل وایرگارد در خارج باید نصب شده باشد یا اگر بدون پنل هستید ، باید وایرگارد در خارج نصب شده باشد.
- لطفا برای کانفیگ دوباره، نخست از منوی uninstall اقدام به حذف تانل کنید تا مشکلی پیش نیاید.
- در آخر هر کانفیگ، ایپی 4 سرور ایران شما با پورت نهایی نمایش داده میشود.
- اگر مشکل huge packet داشتید در هر دو طرف سرور این کامند را اضافه کنید.
 <div align="left">
  
```
 --fix-gro

```
 <div align="right">
  
![Exclamation-Mark-PNG-Clipart](https://github.com/Azumi67/Game_tunnel/assets/119934376/3951d7d9-0e17-4723-b07f-786500ccbc7f)**چند نکته**

- برای تانل ICMP ، حتما اگر اشتباهی در کانفیگ انجام دادید باید حتما هم در سرور ایران و خارج حذفش کنید و هر دو سرور ریبوت شود در غیر این صورت خطای SERVER IS FULL را میگیرید.
- قبل از کانفیگ دوباره، همیشه با دستور ip a مشاهده کنید که tun0 یا tun1 که مربوط به icmp است ، موجود نباشد. حتما پس از Uninstall ICMP سرور خود را ریست نمایید.
- مورد دیگر اینکه، در سرور های ایران اگر DNS مشکل داشته باشد، ممکن است دانلود انجام نشود. حتما از طریق nano /etc/resolv.conf اقدام به تغییر موقتی dns خود بکنید .
- ممکن است در سرور ایران شما، سرعت دانلود پایین باشد و برای همین، ممکنه که دانلود پیش نیاز ها کمی طول بکشد.
- پورت ها در آموزش برای مثال استفاده شده اند، شما میتوانید از پورت های دلخواه خودتان استفاده نمایید.
  </details>
</div>

 ------------------------------------------------------
  <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/update.png" width="40" alt="Image"> </strong>آپدیت</summary>
  
  
------------------------------------ 


- ریست تایمر به صورت دلخواه بر اساس ساعت هم اضافه شد. لاگ های تانل و cache و سرویس ها هر دو ساعت ریست میشود.
- مانند عکس پایین برای اضافه شدن ریست تایمر، تعداد کانفیگ خود را وارد نمایید . من یک عدد کانفیگ داشتم، پس عدد یک را وارد میکنم. باید خودتان عددی را برای ریست تایمر وارد نمایید.
- به جای fix latency از mode 1 استفاده کردم که پینگ را کاهش بده.
- و FEC همچنان مانند قبل بدون تغییر خواهد ماند.
- اگر بر روی ایپی 6 تایم اوت داشتید از ایپی 4 با fec استفاده کنید یا ایپی 6 دیگری بسازید که اختلال برطرف شود.
- اگر موفق نمیشید که fec را پیاده سازی کنید، یا دوباره طبق آموزش جلو بروید یا از گزینه یک ( بدون FEC ) استفاده نمایید.
- اسکریپت بارها تست شده و همه گزینه ها کار میکند.
- اگر اختلالی در تانل داشتید همیشه وارد مسیر روبرو شوید cd /etc/systemd/system و با دستور ls ، سرویس های خارج و ایران را بیابید و با دستور systemctl status servicename و یا journalctl -u servicename.service ، دلیل اختلال تانل را بیابید
  </details>
</div>

------------------
 ------------------------------------------------------
  <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/update.png" width="40" alt="Image"> </strong>آپدیت</summary>
  
  
------------------------------------ 

  <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/right.png" width="40" alt="Image"> اموزش نصب go مورد نیاز برای اجرای اسکریپت</strong></summary>
  
------------------------------------ 

- شما میتوانید از طریق اسکریپت [Here](https://github.com/Azumi67/UDP2RAW_FEC#%D8%A7%D8%B3%DA%A9%D8%B1%DB%8C%D9%BE%D8%AA-%D9%85%D9%86) ، این پیش نیاز را نصب کنید یا به صورت دستی نصب نمایید.
- لطفا پس از نصب پیش نیاز ، برای اجرای اسکریپت go برای بار اول، ممکن تا 10 ثانیه طول بکشد اما بعد از آن سریع اجرا میشود.
- یا به صورت دستی :
```
sudo apt update
arm64 : wget https://go.dev/dl/go1.21.5.linux-arm64.tar.gz
arm64 : sudo tar -C /usr/local -xzf go1.21.5.linux-arm64.tar.gz

amd64 : wget https://go.dev/dl/go1.21.5.linux-amd64.tar.gz
amd64 : sudo tar -C /usr/local -xzf go1.21.5.linux-amd64.tar.gz

nano ~/.bash_profile
paste this into it : export PATH=$PATH:/usr/local/go/bin
save and exit with Ctrl + x , then Y

source ~/.bash_profile
go mod init mymodule
go mod tidy
go get github.com/AlecAivazis/survey/v2
go get github.com/fatih/color

```
- سپس اسکریپت را میتوانید اجرا نمایید.
  </details>
</div>


------------------------
 <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/guidelines.png" width="40" alt="Image"> </strong>پیش نیازها</summary>
  
  
------------------------------------ 
 - لطفا سرور اپدیت شده باشه.
 - میتوانید از اسکریپت اقای [Hwashemi](https://github.com/hawshemi/Linux-Optimizer) و یا [OPIRAN](https://github.com/opiran-club/VPS-Optimizer) هم برای بهینه سازی سرور در صورت تمایل استفاده نمایید. (پیش نیاز نیست)


------------------------
 <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/script.png" width="40" alt="Image">اسکریپت های کارآمد</strong></summary>
------------------------------------   
-
- این اسکریپت ها optional میباشد.


 
 Opiran Scripts
 
```
 bash <(curl -s https://raw.githubusercontent.com/opiran-club/pf-tun/main/pf-tun.sh --ipv4)
```

```
apt install curl -y && bash <(curl -s https://raw.githubusercontent.com/opiran-club/VPS-Optimizer/main/optimizer.sh --ipv4)
```

Hawshemi script

```
wget "https://raw.githubusercontent.com/hawshemi/Linux-Optimizer/main/linux-optimizer.sh" -O linux-optimizer.sh && chmod +x linux-optimizer.sh && bash linux-optimizer.sh
```


------------------------
 <div align="right">
  <details>
    <summary><strong><img src="https://github.com/69learn/6to4-azumi/blob/main/assets/119934376/script.png" width="40" alt="Image">اسکریپت من</strong></summary>
------------------------------------  

- دستور زیر فایل های پیش نیاز را نصب میکند و سپس اقدام به اجرای اسکریپت میکند. اگر مشکلی داشتید به صورت دستی هم میتوانید نصب کنید
```
sudo apt install curl -y  && bash <(curl -s https://raw.githubusercontent.com/Azumi67/UDP2RAW_FEC/main/go.sh)
```

- اگر به صورت دستی نصب کردید و پیش نیاز ها را هم دارید و میخواهید به صورت دستی هم اسکریپت را اجرا کنید میتوانید با دستور زیر اینکار را انجام دهید

  
```
rm udpfec.go
sudo apt install wget -y && wget -O /etc/logo.sh https://raw.githubusercontent.com/Azumi67/UDP2RAW_FEC/main/logo.sh && chmod +x /etc/logo.sh && wget https://raw.githubusercontent.com/Azumi67/UDP2RAW_FEC/main/udpfec.go && go run udpfec.go
```
---------------------------------


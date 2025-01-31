<div dir="rtl" align='justify'>

# آزمایش ١ - آشنایی با سیستم عامل لینوکس

در این جلسه از آزمایشگاه نحوه نصب سیستم عامل لینوکس دستورات اولیه و پرکاربرد این سیستم عامل و همچنین آشنایی با روش های اعمال
تغییرات در هسته ی این سیستم عامل مورد بررسی قرار خواهد گرفت



## ۱.۱ اهداف
انتظار می رود در پایان این جلسه دانشجویان مطالب زیر را فرا گرفته باشند:

آشنایی با نحوه نصب یک توزیع لینوکس به صورت مجازی آشنایی با دستورات اولیه سیستم عامل لینوکس و کار با فایل ها کامپایل و اجرای
کد در محیط لینوکس آشنایی با نحوه اعمال تغییرات در هسته لینوکس کامپایل مجدد و نصب آن


## ۱.۲ پیش نیازها
انتظار می رود که دانشجویان با موارد زیر از پیش آشنا باشند:

برنامه نویسی به زبان ++C/C همچنین نرم افزارهای زیر برای انجام آزمایشات این دستور کار الزامی هستند:

یک نرم افزار برای نصب سیستم عامل مجازی مانند VMware, Desktop Parallels, VirtualBox و ... فایل مورد نیاز برای نصب
سیستم عامل Debian 8



    
# لینک های مفید

* [Download Ubuntu LTS](https://ubuntu.com/download/desktop)
* [Download Debian 8 (jessie)](https://www.debian.org/releases/jessie/debian-installer)
* [Desktop Environments](https://en.wikipedia.org/wiki/Desktop_environment)
* [Package Managers in linux](https://en.wikipedia.org/wiki/Package_manager)
* [Explain Shell Commands](https://explainshell.com/explain?cmd=rm+-rf+temp)
    
# بعضی توزیع های لینوکس

* [Manjaro](https://manjaro.org/)
* [Deepin](https://www.deepin.org/en/)
    
    
## ۱.۳ شرح آزمایش

قبل از شروع آزمایش به یک سوال مهم پاسخ دهیم. چرا کامند میزنیم و چرا shell را یاد میگیریم؟
    
    
### ۱.۳.۱ نصب سیستم عامل لینوکس

به دلیل ساده سازی فرایند اعمال تغییرات در سیستم عامل و همچنین توانایی بازیابی در مقابل خطاهای احتمالی که در این جریان ممکن است
روی دهد، از نسخه مجازی استفاده می کنیم. مناسب است که همواره یک نسخه پشتیبان از سیستم عامل مجازی خود داشته باشید. در تمامی
مراحل آزمایش از رابطه متنی سیستم عامل لینوکس استفاده خواهد شد.

1. یک نسخه از سیستم عامل Debian را با تنظیمات پیش فرض به صورت مجازی نصب کنید. توجه داشته باشید که برای کامپایل هسته
نیاز به حداقل ٢٠ گیگابایت فضا خواهید داشت، بنابراین در هنگام ایجاد سیستم عامل مجازی آن را در نظر بگیرید. حداقل حافظه مورد
نیاز نیز ۵١٢ مگابایت خواهد بود.

1. نصب سیستم عامل را به صورت کمینه (minimal) انجام دهید. به این ترتیب تنها بسته های ضروری نصب خواهند شد. برای این کار
کافی است در هنگام نصب در گام Selection Software تنها گزینه ی System Standard را انتخاب کنید.
در صورت نیاز به جزئیات و راهنمایی هایی بیشتر به [اینجا](http://tuxonomy.wordpress.com/2010/04/15/debian-minimal-install-of-a-base-system-lenny-) مراجعه کنید.


### ۱.۳.۲ آشنایی با دستورات پایه ی لینوکس
برای دریافت راهنمایی در مورد هرکدام از دستورات ارائه شده در ادامه می توانید از دستور man [command] استفاده کنید. در گزارش خود،
دستورات مورد استفاده در هریک از مراحل زیر را بیاورید.

البته استفاده از [tldr](https://github.com/isacikgoz/tldr) هم در بسیاری از موارد توصیه می شود.
    
1. به کمک دستور pwd آدرس دایرکتوری جاری را نمایش دهید.

1. به کمک دستور cd به داخل دایرکتوری tmp/ رفته و به کمک دستور mkdir یک پوشه به نام oslab1 ایجاد کنید.

1.  کمک ویراشگر nano یک فایل متنی با محتوای نام و شماره ی دانشجویی خود به اسم informantion.txt ایجاد کنید و در نهایت از
ویراشگر خارج شوید.

1. به کمک دستور mv نام فایل را به myinformation.txt تغییر دهید.

1.  .به کمک دستور cp یک کپی از این فایل به اسم backupinfo.txt را در همان شاخه ایجاد کنید.

1. محتوای فایل myinformation.txt را به کمک دستور cat نشان دهید.

1. دستورات زیر را اجرا کنید:

    <div dir="ltr">

    ```shell
    echo "Hello There!" > myinformation.txt
    echo "Hello World!" >> myinformation.txt
    ```


    </div>
    
    تفاوت دو خط بالا را شرح دهید.

1. یک فایل متنی جدید با محتوای دلخواه را به کمک دستور cat (بدون استفاده از nano) به نام testfile.txt ایجاد کنید.

1. لیست پردازه های در حال اجرا را به کمک دستور aux ps نمایش دهید.

1. به کمک دستور grep لیست پردازه هایی را نشان دهید که در نام آن ها حرف a وجود دارد.

1. به کمک دستور cd به داخل شاخه‌ی /usr/bin رفته و به کمک دستور ls لیست فایل های موجود در آن را نمایش دهید. فایل های موجود
در این پوشه بخشی از دستورات قابل اجرا در سیستم هستند.


1. به کمک دستور ls و استفاده از پارامتر های مناسب، علاوه بر نام فایل ها، حجم آن ها را نمایش دهید.

1. به کمک دستور grep لیست فایل های در این پوشه را نشان دهید که در آن ها کلمه fs یا ld وجود دارد.

## ۱.۴ فعالیت‌ها

*  کاربرد دستورات زیر را به اختصار بیان کنید:
    <div dir="ltr">

    ```shell
    cut
    find
    head
    tail
    touch
    wc
    kill
    ```
    
    </div>
* با کمک دستوراتی که فراگرفته اید، فرمان هایی برای اعمال زیر بنویسید:
    * پیدا کردن تعداد خطوط در یک فایل متنی به نام mybook.txt
    * پیدا کردن تعداد فایل هایی که با حرف A شروع می شوند.
    * پیدا کردن حجم فایل mybook.txt


### ۱.۴.۱ اعمال تغییرات و کامپایل مجدد هسته ی سیستم عامل

1. ابتدا کد منبع هسته را دریافت کنید. برای این کار از دستور زیر استفاده کنید:
    <div dir="ltr">

    ```shell
    apt-get install linux-source-3.2
    ```
        
    </div>
1. ابزار های لازم برای کامپایل و نصب هسته را دریافت کنید:
    <div dir="ltr">

    ```shell
    apt-get install build-essential fakeroot
    apt-get build-dep linux
    ```
        
    </div>

1. به کمک دستور زیر، کد های هسته را در یک پوشه مشخص بازگشایی کنید:
    <div dir="ltr">

    ```shell
    apt-get source linux
    ```
        
    </div>

1. یک پوشه با نام linux-source-3.2 ایجاد شده که حاوی کد هسته ی لینوکس می باشد.



### ۱.۴.۲ فعالیت‌ها
 به کمک [اینجا](https://www.linux.com/topic/desktop/how-compile-linux-kernel-0/) نحوه کامپایل کردن هسته و نصب آن را به اختصار بیان کنید. سپس هسته ی سیستم عامل را یک بار کامپایل نمایید. در دفعه
اول این کار زمان گیر خواهد بود، ولی عملیات را برای دفعات بعد تسریع خواهد کرد.


</div>


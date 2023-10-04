میخوایم مراحل نصب کردن laravel/installer رو توی سیستم Arch با هم دیگه جلو بریم

برای این کار اول از به خاطر مساعل تحریم به ی فیلترشکن وصل شی که من اینجا از شکن استفاده میکنم

sudo vim /etc/resolv.conf

و بعد از باز کردن این فایل DNS پایین رو قرار بدین داخلش

nameserver 178.22.122.100
nameserver 185.51.200.2

بعد کامند زیر رو داخل ترمینال اجرا کنید

composer global require laravel/installer

بعد از نصب کردن اگر بریم توی terminal و command زیر رو بزنیم میبینیم که برای ما کار نمیکنه

laravel new project-name

چون terminal به مسیر پایین دسترسی نداره و نمیشناسه

composer/vendor/bin

برای حل کردن این مشگل ما توی فایل پایین کامند زیر رو کپی میکنیم

vim ~/.bashrc

export PATH=~/.config/composer/vendor/bin:$PATH

و بعد دستور پایین رو اجرا میکنیم 

source ~/.bashrc

الان میتونیم بریم به با استفاده از command زیر توی مسیر های 

/var/www/html or /srv/http بستگی به توزیعی داره که استفاده میکنین

laravel new project-name

الان برای ما کار میکنه 


نکته: اگر از ZSH استفاده میکنین باید به صورت زیر عمل کنید

vim ~/.zshrc

export PATH=~/.config/composer/vendor/bin:$PATH

source ~/.zshrc

و بعد مثل قبل



برای آپدیت کردن laravel/installer از کامند زیر استفاده کنید

composer global update laravel/installer

Building a new version of php-base

1. clone opencats/php-base into your own github
amend it
then locally

1148  git clone --depth 1 https://github.com/russh/php-base  
 1149  cd php-base/  
 1150  docker build -t russh/php-base:your-tag-goes-here .  

Push it up to Docker hub  
 1212  docker push russh/php-base:7.2-fpm-alpine  
 
 once its working push it to opencats docker hub  
 
 docker push opencats/php-base:7.2-fpm-alpine  
 

 
 ***
 need this to add in mcrypt support in php 7.2 from PECL  
 Follow this: https://lukasmestan.com/install-mcrypt-extension-in-php7-2/
 
Note: we omit 
sudo bash -c "echo extension=/usr/local/lib/php/extensions/no-debug-non-zts-20170718/mcrypt.so > /etc/php/7.2/cli/conf.d/mcrypt.ini"  
sudo bash -c "echo extension=/usr/local/lib/php/extensions/no-debug-non-zts-20170718/mcrypt.so > /etc/php/7.2/apache2/conf.d/mcrypt.ini"
 

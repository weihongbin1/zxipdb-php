[![Build Status](https://www.travis-ci.org/ZX-Inc/zxipdb-php.svg?branch=main)](https://travis-ci.com/github/ZX-Inc/zxipdb-php)
<a href="https://packagist.org/packages/ZX-Inc/zxipdb-php"><img src="https://img.shields.io/packagist/dt/ZX-Inc/zxipdb-php" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/ZX-Inc/zxipdb-php"><img src="https://img.shields.io/packagist/v/ZX-Inc/zxipdb-php" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/ZX-Inc/zxipdb-php"><img src="https://img.shields.io/packagist/l/ZX-Inc/zxipdb-php" alt="License"></a>
<a href="https://www.php.net"><img src="https://img.shields.io/badge/php-%3E%3D%205.6-8892BF.svg?style=flat-square" alt="PHP Version >= 5.6"></a>


## IPv4/IPv6 offline address database.IPv4/IPv6双栈地址离线数据库。IPv4 by 纯真网络，IPv6 by ZX Inc.
##### Being updating every <font color=#FF0000 size=36>5</font> days 每<font color=#FF0000 size=36>5</font>天更新一次

### IPv4 address locations by 纯真网络
database updated at <font color=#FF0000 size=36>2021-09-08</font> with <font color=#FF0000 size=36>528346</font> records

### IPv6 address locations by Zx Inc.
database updated at <font color=#FF0000 size=36>2021-07-26</font> with <font color=#FF0000 size=36>178724</font> records

### Usage/使用方法
```shell script
composer require zx-inc/zxipdb
```
Your code/你的业务代码
```php
$result = \ZxInc\Zxipdb\IPTool::query('8.8.8.8');
/*
$result = [
    "start" => "8.8.8.8"
    "end" => "8.8.8.8"
    "addr" => array:2 [
        0 => "美国"
        1 => "加利福尼亚州圣克拉拉县山景市谷歌公司DNS服务器"
    ]
    "disp" => "美国 加利福尼亚州圣克拉拉县山景市谷歌公司DNS服务器"
]
 */
$result = \ZxInc\Zxipdb\IPTool::query('240e:e9:8819:0:3::3f9');
/*
$result = [
    "start" => "240e:e9:8800::"
    "end" => "240e:e9:8fff:ffff::"
    "addr" => array:2 [
        0 => "中国江苏省苏州市"
        1 => "中国电信IDC"
    ]
    "disp" => "中国江苏省苏州市 中国电信IDC"
]
 */
$valid = \ZxInc\Zxipdb\IPv4Tool::isValidAddress('114.114.114.114');
/*
$valid = true;
 */
$valid = \ZxInc\Zxipdb\IPv6Tool::isValidAddress('240e:e9:8819:0:3::3f9');
/*
$valid = true;
 */

```

### Notice/使用提示
- We don't recommend forking this repository/不推荐fork此仓库
- We recommend using linux's crontab to update ip database/推荐使用linux计划任务定期更新数据库

### Auto update database/自动更新数据库
```shell
crontab -e
# add line/增加一行，每小时更新一次
0 * * * * * cd /var/www/your_project && composer require zx-inc/zxipdb
```



### Official Website/官方网站
- [纯真IPv4数据库](https://www.cz88.net/)
- [IPv6地址查询工具 Hongkong/Tokyo](http://ip.zxinc.org)
- [IPv6地址查询工具 Ningbo](https://ip.shanshan-business.com)
- [IPv6地址查询工具 Beijing](https://ip.yinghualuo.cn)

### Author Blog/作者博客
- [Charles的小星球](https://blog.yinghualuo.cn)

### QQ Group/QQ交流群
- RTBAsia x 纯真IP技术组   482139657
- ZX IPv6地址库交流群       23871048

### Sponsor/赞助
![QrCode](https://blog.yinghualuo.cn/blog/2020/11/sponsor.png)

### License/使用协议
ZxIpAddress is licensed under [MIT](https://github.com/ZX-Inc/zxipdb-php/blob/main/LICENSE).


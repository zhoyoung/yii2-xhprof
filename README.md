#yii2-xhprof
xhprof for yii2
========================

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require zhoyoung/yii2-xhprof "*"
```

for dev-master

```
php composer.phar require zhoyoung/yii2-xhprof "dev-master"
```

or add

```
"zhoyoung/yii2-xhprof": "*"
```

to the require section of your `composer.json` file.


Usage
-----

1. add the following code to your entry script,for example: index.php
```php
defined('YII_ENV') or define('YII_ENV', 'dev');
```

2. then modify your application configuration as follows at the end of your config file:

```php
if (YII_ENV_DEV){
    $config['bootstrap'][] = 'xhprof';
    $config['modules']['xhprof'] = [
        'class'=>'zhoyoung\xhprof\Module',
        //控制抓取频率，如果为1则全部抓取
        'frequency' => 1,
        //超过限制秒数就抓取
        'minExcutionTime' => 1,
        //默认源Yii::$app->id
		//'name'=>'linkserver',
		//记录路径，默认: @runtime/xhprof/
		//'dir'=>'/tmp',
	];
}
```

3. then you browse the profs var http://your.site.name/xhprof

[youngSvip@163.com]
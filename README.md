Yii 2 Basic Mailer
============================

Это пример простого Yii 2 приложения для отправки почты.
Используется встроенный в Yii 2 модуль swiftmailer

Системные требования
------------

Версия PHP миниму 5.4.0.

Любой web-сервер

Установка
------------

~~~ 
git clone https://github.com/danvop/mailer.git mailer

cd mailer

composer install
~~~

В настройках web-сервера прописать в качестве точки входа папку /mailer/web/

далее в файле /config/web.php приложения изменить настройки для пункта 'mail'
~~~
//пример для отправки через gmail.com
        'mail' => [
        'class' => 'yii\swiftmailer\Mailer',
        'useFileTransport' => false,
        'transport' => [
            'class' => 'Swift_SmtpTransport',
            'host' => 'smtp.gmail.com',
            'username' => 'username@gmail.com',
            'password' => 'password',
            'port' => '587',
            'encryption' => 'tls',
                        ],
        ],
~~~

~~~
//пример для отправки через MS Exchange
        'mailer' => [
            'class' => 'yii\swiftmailer\Mailer',
            'useFileTransport' => false,
            'transport' => [
            'class' => 'Swift_SmtpTransport',
            'host' => 'exchange.example.com', //вставляем имя или адрес почтового сервера
            'username' => '', 
            'password' => '',
            'port' => '25',
            'encryption' => '',
            ],
        ],
~~~

### Install from an Archive File

Extract the archive file downloaded from [yiiframework.com](http://www.yiiframework.com/download/) to
a directory named `basic` that is directly under the Web root.

Set cookie validation key in `config/web.php` file to some random secret string:

```php
'request' => [
    // !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
    'cookieValidationKey' => '<secret random string goes here>',
],
```

You can then access the application through the following URL:

~~~
http://localhost/basic/web/
~~~


### Install via Composer

If you do not have [Composer](http://getcomposer.org/), you may install it by following the instructions
at [getcomposer.org](http://getcomposer.org/doc/00-intro.md#installation-nix).

You can then install this project template using the following command:

~~~
php composer.phar global require "fxp/composer-asset-plugin:~1.1.1"
php composer.phar create-project --prefer-dist --stability=dev yiisoft/yii2-app-basic basic
~~~

Now you should be able to access the application through the following URL, assuming `basic` is the directory
directly under the Web root.

~~~
http://localhost/basic/web/
~~~


CONFIGURATION
-------------

### Database

Edit the file `config/db.php` with real data, for example:

```php
return [
    'class' => 'yii\db\Connection',
    'dsn' => 'mysql:host=localhost;dbname=yii2basic',
    'username' => 'root',
    'password' => '1234',
    'charset' => 'utf8',
];
```

**NOTES:**
- Yii won't create the database for you, this has to be done manually before you can access it.
- Check and edit the other files in the `config/` directory to customize your application as required.
- Refer to the README in the `tests` directory for information specific to basic application tests.

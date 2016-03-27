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


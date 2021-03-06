---
layout: article
title: "Добавление манифеста веб-приложения"
description: "Манифест веб-приложения представляет собой простой файл JSON, с помощью которого разработчик может управлять отображением своего приложения на экранах различных устройств (например, на экране мобильного устройства), указывать элементы, которые могут быть запущены пользователем, а также, что крайне важно, определять способы запуска веб-приложения. Манифест предоставляет широчайшие возможности управления приложением, однако сейчас мы рассмотрим способы запуска приложения"
introduction: "Манифест веб-приложения представляет собой простой файл JSON, с помощью которого разработчик может управлять отображением своего приложения на экранах различных устройств (например, на экране мобильного устройства), указывать элементы, которые могут быть запущены пользователем, а также, что крайне важно, определять способы запуска веб-приложения. Манифест предоставляет широчайшие возможности управления приложением, однако сейчас мы рассмотрим способы запуска приложения"
article:
  written_on: 2014-12-17
  updated_on: 2014-12-17
  order: 1
id: wapp-app-manifest
collection: stickyness
authors:
  - mattgaunt
  - paulkinlan
collection: stickyness
priority: 1
key-takeaways:
  manifest:
    - Укажите набор значков, которые будут отображаться на устройствах с любыми размерами и характеристиками
    - Выберите подходящее `short_name`, поскольку это имя будет отображаться на экране
    - Добавьте URL-адрес для запуска и параметр QueryString, чтобы можно было отслеживать данные о количестве запусков приложения
---

{% wrap content %}

{% include modules/takeaway.liquid list=page.key-takeaways.manifest %}

Добавить манифест веб-приложения не составляет никакого труда. Достаточно создать файл manifest.json
с необходимыми для веб-приложения настройками и ресурсами,
а затем добавить *ссылку* на него в HTML-код страниц своего сайта.

## Создание манифеста

Файлу манифеста можно присвоить любое имя, однако в большинстве случаев ему присваивают имя manifest.json. Ниже показан пример файла манифеста.

{% highlight json %}
{
  "short_name": "Kinlan's Amaze App",
  "name": "Kinlan's Amazing Application ++",
  "icons": [
    {
      "src": "launcher-icon-0-75x.png",
      "sizes": "36x36"
    },
    {
      "src": "launcher-icon-1x.png",
      "sizes": "48x48"
    },
    {
      "src": "launcher-icon-1-5x.png",
      "sizes": "72x72"
    },
    {
      "src": "launcher-icon-2x.png",
      "sizes": "96x96"
    },
    {
      "src": "launcher-icon-3x.png",
      "sizes": "144x144"
    },
    {
      "src": "launcher-icon-4x.png",
      "sizes": "192x192"
    }
  ],
  "start_url": "index.html",
  "display": "standalone"
}
{% endhighlight %}

Следует указать значение для параметра *short_name*, поскольку оно будет использоваться при запуске приложения.

Если не указать значение для параметра *start_url*, то будет использоваться текущая страница, которая представляет собой не совсем то, что хотят увидеть пользователи.

## Предоставление браузеру сведений о манифесте

После создания манифеста и его добавления на сайт достаточно лишь добавить на все страницы вашего веб-сайта соответствующий тег "link", как показано ниже.

{% highlight html %}
<link rel="manifest" href="/manifest.json">
{% endhighlight %}

## Создание привлекательных значков приложения для устройства

Можно определить набор значков, которые будут использоваться браузером и отображаться на главном экране устройства пользователя.

Определить значки для вашего приложения можно так, как показано в примере кода выше, указав тип, размер и разрешение значка, однако не обязательно указывать их все – размеров и источника изображения будет достаточно.

{% highlight json %}
"icons": [{
    "src": "images/touch/icon-128x128.png",
    "sizes": "128x128"
  }, {
    "src": "images/touch/apple-touch-icon.png",
    "sizes": "152x152"
  }, {
    "src": "images/touch/ms-touch-icon-144x144-precomposed.png",
    "sizes": "144x144"
  }, {
    "src": "images/touch/chrome-touch-icon-192x192.png",
    "sizes": "192x192"
  }],
{% endhighlight %}

<div class="clear g-wide--full">
    <figure>
        <img src="images/homescreen-icon.png" alt="Добавление значка на главный экран">

        <figcaption>Добавление значка на главный экран</figcaption>
    </figure>
</div>

<div class="clear"></div>

## Настройка способа открытия сайта

Чтобы при запуске вашего веб-приложения скрывался пользовательский интерфейс браузера, задайте для параметра *display* значение *standalone*.

{% highlight json %}
"display": "standalone"
{% endhighlight %}

Если вы считаете, что пользователям будет удобнее работать с приложением как с обычным сайтом в браузере, задайте для параметра "display" значение "browser".

{% highlight json %}
"display": "browser"
{% endhighlight %}

<div class="clear g-wide--full">
    <figure class="fluid">
        <img src="images/manifest-display-options.png" alt="web-app-capable">

        <figcaption>Варианты отображения в манифесте</figcaption>
    </figure>
</div>

<div class="clear"></div>

## Укажите исходную ориентацию страницы

Можно принудительно указать определенную ориентацию страницы, что действительно полезно в некоторых случаях, например в играх, которые могут работать только в альбомной ориентации. Однако это следует делать с осторожностью. Пользователи предпочитают иметь возможность работать с приложениями в обоих вариантах ориентации.

{% highlight json %}
"orientation": "landscape"
{% endhighlight %}

<div class="clear g-wide--full">
    <figure class="fluid">
        <img src="images/manifest-orientation-options.png" alt="Варианты ориентации в манифесте веб-приложения">

        <figcaption>Варианты ориентации в манифесте веб-приложения</figcaption>
    </figure>
</div>

<div class="clear"></div>

## Можно ли использовать эту функцию на сегодняшний день? Поддерживается ли она браузерами?

Да, несомненно.  Это передовая функция, реализация которой в приложении позволит значительно повысить удобство 
его использования в браузерах с поддержкой манифеста.  Даже если браузер не поддерживает манифест, пользователи по-прежнему смогут работать с сайтом.


По состоянию на ноябрь 2014 г. поддержка манифеста реализована в браузере Chrome. В Mozilla поддержка манифеста находится на стадии реализации, [а для IE изучается возможность внедрения такой функциональности](https://status.modern.ie/webapplicationmanifest?term=manifest).

{% include modules/nextarticle.liquid %}

{% endwrap %}

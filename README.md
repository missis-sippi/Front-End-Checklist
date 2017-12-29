# Чек-лист фронтенда
[![Соавторы](https://img.shields.io/github/contributors/thedaviddias/Front-End-Checklist.svg)](https://github.com/thedaviddias/Front-End-Checklist/graphs/contributors)
[![Лицензия CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

**Чек-лист фронтенда** — исчерпывающий список элементов, которые необходимо внедрить и проверить перед запуском вашего сайта/HTML-страницы.

Список основан на годах опыта фронтенд-разработки, с некоторыми дополнениями из других чек-листов, находящихся в открытом доступе.

## Содержание

1. **[Как использовать](#Как-использовать)**
2. **[Раздел заголовка — тег `<head>`](#Раздел заголовка--тег-head)**
3. **[HTML](#html)**
4. **[Веб-шрифты](#Веб-шрифты)**
5. **[CSS](#css)**
6. **[Изображения](#Изображения)**
7. **[JavaScript](#javascript)**
8. **[Безопасность](#security)**
9. **[Производительность](#performance-1)**
10. **[Доступность](#accessibility)**
11. **[SEO](#seo)**
12. **[Перевод](#translation)**
13. **[Содействие](#contributing)**

## Как использовать

Для большинства проектов необходимо соблюдать все пункты **чек-листа фронтенда**, однако некоторые элементы могут быть опущены или не являются необходимыми в конкретном случае (например, в случае управления веб-приложением RSS-лента не понадобится). Будем использовать 3 уровня важности требований:

* ![Низкий][low_img] означает, что элемент **рекомендуется** использовать, но в некоторых ситуациях его можно опустить.
* ![Средний][medium_img] означает, что этот элемент **настоятельно рекомендуется** использовать, и пренебречь им можно лишь в отдельных исключительных случаях. Отсутствие некоторых таких элементов может негативно повлиять на производительность или поисковую оптимизацию сайта (SEO).
* ![Высокий][high_img] означает, что элемент **ни в коем случае** нельзя исключать. Отсутствие элемента может вызвать нарушение функциональности сайта, проблемы с доступностью и SEO. В первую очередь при тестировании необходимо проверить данные элементы.

Ссылки на некоторые ресурсы помечены специальными иконками, помогающими определить тип контента:

* 📖: документация либо статья
* 🛠: онлайн-инструмент / инструмент тестирования
* 📹: медиа или видеоконтент

---

## Раздел заголовка — тег `<head>`

> **Примечание:** [Список всех элементов](https://github.com/joshbuchea/HEAD), которые могут размещаться в теге `head` HTML-документа.

### Метатеги

* [ ] **Doctype:** ![Высокий][high_img] Используйте **Doctype** HTML5, подключив его в самой первой строке каждой HTML-страницы.

```html
<!-- Doctype HTML5 -->
<!doctype html>
```

> 📖 [Determining the character encoding - HTML5 W3C](https://www.w3.org/TR/html5/syntax.html#determining-the-character-encoding)

*Три следующих метатега (Charset, X-UA Compatible и Viewport) должны быть первыми в теге `head`.*

* [ ] **Кодировка:** ![Высокий][high_img] Объявленная кодировка (UTF-8) задана правильно.

```html
<!-- Задание кодировки документа -->
<meta charset="utf-8">
```

* [ ] **X-UA-Compatible:** ![Средний][medium_img] Метатег `X-UA-Compatible` должен присутствовать.

```html
<!-- Указание использовать наиболее новый доступный режим отображения для Internet Explorer -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
```

> 📖 [Specifying legacy document modes (Internet Explorer)](https://msdn.microsoft.com/en-us/library/jj676915(v=vs.85).aspx)

* [ ] **Viewport:** ![Высокий][high_img] `viewport` должен быть правильно объявлен.

```html
<!-- Viewport для адаптивных веб-страниц -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

* [ ] **Title:** ![Высокий][high_img] Тег `title` используется на всех страницах (SEO: не более 65 символов, включая название сайта).

```html
<!-- Заголовок документа -->
<title>Заголовок страницы, занимающий не более 65 символов</title>
```

> 📖 [Title - HTML | MDN](https://developer.mozilla.org/ru/docs/Web/HTML/Element/title)

* [ ] **Description:** ![Высокий][high_img] Метаописание (`description`) существует, является уникальным и содержит не более 150 символов.

```html
<!-- Метаописание -->
<meta name="description" content="Описание страницы, содержащее не более 150 символов">
```

* [ ] **Фавиконки:** ![Средний][medium_img] Каждый значок-favicon создан и отображается корректно. Если используется только `favicon.ico`, то он должен быть помещен в корневой каталог сайта. Обычно никакой дополнительной разметки не требуется, но тем не менее, хорошей практикой является явное указание пути к файлу в атрибуте `href` — как в примере ниже. Как более современный вариант, ** рекомендуется использовать формат PNG** вместо формата `.ico`(размеры: 32x32px).

```html
<!-- Стандартная фавиконка -->
<link rel="icon" type="image/x-icon" href="https://example.com/favicon.ico">
<!-- Рекомендуемый формат фавиконки -->
<link rel="icon" type="image/png" href="https://example.com/favicon.png">
```

> * 🛠 [Favicon Generator](https://www.favicon-generator.org/)
> * 🛠 [RealFaviconGenerator](https://realfavicongenerator.net/)
> * 📖 [Favicon Cheat Sheet](https://github.com/audreyr/favicon-cheat-sheet)
> * 📖 [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? - CSS Tricks](https://css-tricks.com/favicon-quiz/)
> * 📖 [PNG favicons - caniuse](https://caniuse.com/#feat=link-icon-png)

* [ ] **Apple Touch Icon:** ![Low][low_img] Присутствует фавиконка для тач-устройств Аpple apple-mobile-web-app-capable. *(Создайте файл иконки для устройств Apple, имеющий размер как минимум 200x200px — для поддержки всех размеров, которые могут потребоваться)*

```html
<!-- Apple Touch Icon -->
<link rel="apple-touch-icon" href="/custom-icon.png">
```

> 📖 [Configuring Web Applications](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

* [ ] **Canonical:** ![Средний][medium_img] Используйте `rel="canonical"`, чтобы избежать дублирования контента.

```html
<!-- Помогает предотвратить дублирование контента -->
<link rel="canonical" href="http://example.com/2017/09/a-new-article-to-red.html">
```

### HTML-теги

* [ ] **Атрибут lang:** ![Высокий][high_img] Языковой атрибут `lang` используется и соответствует языку, используемому на данной странице.

```html
<html lang="en">
```

* [ ] **Атрибут dir:** ![Средний][medium_img] Направление отображения текста задано с помощью атрибута `dir` тега `body` (атрибут `dir` можно использовать и в других HTML-тегах).

```html
<html dir="rtl">
```

> 📖 [dir - HTML | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)

* [ ] **Альтернативный язык:** ![Низкий][low_img] Указан альтернативный язык, соответствующий языку текущей страницы.

```html
<link rel="alternate" href="https://es.example.com/" hreflang="es">
```

* [ ] **Условные комментарии:** ![Низкий][low_img] Conditional comments are present for IE if needed.

> 📖 [About conditional comments (Internet Explorer) - MSDN - Microsoft](https://msdn.microsoft.com/en-us/library/ms537512(v=vs.85).aspx)

* [ ] **RSS-лента:** ![Низкий][low_img] Если сайт является блогом или используется для размещения статей, предусмотрена ссылка на RSS.

* [ ] **Критичный CSS:** ![Средний][medium_img] Критический CSS (элементы, показываемые в видимой части экрана — "above the fold") включает в себя CSS, использующийся для отображения видимой части страницы. Он встроен до вызова основного CSS между тегами `<style></style>` в одну строку (минифицирован).

> 🛠 [Critical by Addy Osmani on Github](https://github.com/addyosmani/critical)

* [ ] **CSS order:** ![Высокий][high_img] Все CSS-файлы загружаются до любого из JavaScript-файлов в `<head>`. (Кроме случая, когда JS-файлы загружаются асинхронно вверху страницы).

### Метатеги для социальных сетей

Крайне рекомендуется использовать ***Facebook OG*** и ***Twitter Cards*** на любом сайте. Другие метатеги могут быть использованы, если вы намерены присутствовать в других социальных медиа и важно обеспечить отображение.

* [ ] **Facebook Open Graph:** ![Низкий][low_img] Разметка Facebook Open Graph (OG) протестирована, присутствует на всех страницах и содержит верную информацию. Размер изображений — минимум 600 x 315 пикселей, рекомендованный размер — 1200 x 630 пикселей.

```html
<meta property="og:type" content="website">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
```

> * 📖 [A Guide to Sharing for Webmasters](https://developers.facebook.com/docs/sharing/webmasters/)
> * 🛠 Протестируйте вашу страницу с помощью [Отладчика перепостов](https://developers.facebook.com/tools/debug/)

* [ ] **Twitter Card:** ![Низкий][low_img]

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

> * 📖 [Getting started with cards — Twitter Developers](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started)
> * 🛠 Протестируйте вашу страницу с помощью [Валидатора Twitter card](https://cards-dev.twitter.com/validator)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## HTML

### Лучшие практики

* [ ] **Семантические элементы HTML5:** ![Высокий][high_img] Семантические элементы HTML5 используются соответствующим образом (`header`, `section`, `footer`, `main` и т.д.).

> 📖 [Справочник по HTML](http://htmlreference.io/)

* [ ] **Страницы ошибок:** ![Высокий][high_img] Страницы 404 и 5xx ошибок должны существовать. Помните, что страница ошибок 5xx должна иметь встроенный CSS (без внешнего вызова на текущем сервере).

* [ ] **Noopener:** ![Средний][medium_img] В случае использования внешних ссылок с `target="_blank"` ссылкам также необходимо добавить атрибут `rel="noopener"`, чтобы предотвратить уязвимость !! в to prevent tab nabbing. Если необходима поддержка старых версий Firefox, используйте `rel="noopener noreferrer"`.

> 📖 [Про rel=noopener](https://mathiasbynens.github.io/rel-noopener/)

* [ ] **Удалите лишние комментарии:** ![Низкий][low_img] Ненужный код должен быть удален перед запуском сайта.

### Валидация HTML

* [ ] **W3C-совместимость:** ![Высокий][high_img] Все страницы должны быть протестированы с помощью валидатора W3C для выявления возможных проблем в коде.

> 🛠 [W3C validator](https://validator.w3.org/)

* [ ] **HTML Lint:** ![Высокий][high_img] Я использую инструменты, помогающие проанализировать возможные проблемы с HTML-кодом.

> 🛠 [Dirty markup](https://dirtymarkup.com/)

* [ ] **Десктопные браузеры:** ![Высокий][high_img] Все страницы протестированы во всех современных десктопных браузерах (Safari, Firefox, Chrome, Internet Explorer, EDGE и т.д.).

* [ ] **Мобильные браузеры:**  ![Высокий][high_img] Все страницы протестированы во всех современных мобильных браузерах (системный браузер, Chrome, Safari и т.д.).

* [ ] **Проверка ссылок:** ![Высокий][high_img] На всех страницах не должно быть «битых» ссылок. Убедитесь, что на сайте нет ошибок 404.

> 🛠 [Сервис проверки ссылок W3C](https://validator.w3.org/checklink)

* [ ] **Тестирование блокировщиков рекламы:** ![Средний][medium_img] Веб-сайт должен корректно отображать контент при включенном блокировщике рекламы (вы можете также предусмотреть сообщение, побуждающее пользователя отключить блокировщик для максимально корректного отображения страниц).

- [ ] **Pixel perfect:** ![Высокий][high_img] Страницы сверстаны практически пиксель в пиксель, внешне максимально приближены к макетам. Необязательно добиваться 100-процентного совпадения, однако верстка должна быть максимально близка к исходному макету.

> [Pixel Perfect - расширение для Chrome](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=ru)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Веб-шрифты

* [ ] **Форматы веб-шрифтов:** ![Высокий][high_img] Форматы WOFF, WOFF2 and TTF поддерживаются всеми современными браузерами.

> * 📖 [WOFF - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff).
> * 📖 [WOFF 2.0 - Web Open Font Format - Caniuse](https://caniuse.com/#feat=woff2).
> * 📖 [TTF/OTF - TrueType and OpenType font support](https://caniuse.com/#feat=ttf)
> * 📖 [Using @font-face - CSS-Tricks](https://css-tricks.com/snippets/css/using-font-face/)

* [ ] **Размер файла веб-шрифтов:** ![Высокий][high_img] Размер веб-шрифтов не должен превышать 2 МБ (включая все начертания).

**[⬆ обратно к содержанию](#table-of-contents)**

---

## CSS

> **Примечание:** Обратите внимание на [рекомендации по CSS](https://cssguidelin.es/) и [рекомендации по Sass](https://sass-guidelin.es/), которых придерживается большинство фронтенд-разработчиков. Если у вас появились сомнения насчет какого-либо CSS-свойства, можете использовать [справочник CSS](http://cssreference.io/).

* [ ] **Адаптивный веб-дизайн:** ![Высокий][high_img] На сайте должна использоваться адаптивная верстка.
* [ ] **CSS печатной версии:** ![Средний][medium_img] Для каждой страницы используются корректные CSS-стили для печати.
* [ ] **Препроцессоры:** ![Средний][medium_img] Your page is using a CSS preprocessor ([Sass](http://sass-lang.com/) предпочтителен).
* [ ] **Уникальные идентификаторы:** ![Высокий][high_img] Если используются идентификаторы (`id`), то в пределах страницы они должны быть уникальными.
* [ ] **Сброс стилей:** ![Высокий][high_img] Используется современный вариант сброса CSS-стилей. *(Если вы используете CSS-фреймворк, такой как Bootstrap или Foundation, Normalize уже включен в него.)*

> * 📖 [Reset.css](https://meyerweb.com/eric/tools/css/reset/)
> * 📖 [Normalize.css](https://necolas.github.io/normalize.css/)
> * 📖 [Reboot](https://getbootstrap.com/docs/4.0/content/reboot/)

* [ ] **JS-префиксы:** ![Низкий][low_img] Все классы и идентификаторы, используемые в JS-файлах, начинаются с **js-** и не стилизуются в CSS-файлах.

```html
<div id="js-slider" class="my-slider">
<!-- Or -->
<div id="id-used-by-cms" class="js-slider my-slider">
```

* [ ] **Встроенные (embedded) и инлайновые стили:** ![Высокий][high_img] Любой ценой избегайте использования встроенного или инлайнового CSS: использовать их допустимо только по действительно веским причинам (например, `background-image` для слайдера, критический CSS).
* [ ] **Vendor prefixes:** ![Высокий][high_img] CSS vendor prefixes are used and are generated accordingly with your browser support compatibility.

> 🛠 [Autoprefixer CSS online](https://autoprefixer.github.io/)

### Производительность

- [ ] **Объединение:** ![Высокий][high_img] Все CSS-файлы объединены в один файл. *(Не для HTTP/2)*
- [ ] **Минификация:** ![Высокий][high_img] Все CSS-файлы должны быть минифицированы.
- [ ] **Неблокирующий CSS:** ![Средний][medium_img] CSS-файлы должны быть неблокирующими, чтобы не задерживать загрузку DOM.

> * 📖 [loadCSS by filament group](https://github.com/filamentgroup/loadCSS)
> * 📖 [Example of preload CSS using loadCSS](https://gist.github.com/thedaviddias/c24763b82b9991e53928e66a0bafc9bf)

- [ ] **Неиспользуемый CSS:** ![Низкий][low_img] Избавьтесь от неиспользуемого CSS-кода.

> * 🛠 [UnCSS Online](https://uncss-online.com/) 🛠
> * 🛠 [PurifyCSS](https://github.com/purifycss/purifycss)
> * 🛠 [Chrome DevTools Coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage)


### Тестирование CSS

* [ ] **Линтинг (предотвращение ошибок) CSS:** ![Высокий][high_img] Все CSS или SCSS файлы не должны содержать ошибок.

> * 🛠 [stylelint, линтер CSS](https://stylelint.io/)
> * 📖 [Справочник по Sass](https://sass-guidelin.es/)

* [ ] **Адаптивный веб-дизайн:** ![Высокий][high_img] Все страницы были протестированы на следующих контрольных точках: 320px, 768px, 1024px (их может быть и больше, либо они могут быть другими в зависимости от требований).

* [ ] **Валидатор CSS:** ![Средний][medium_img] CSS протестирован, выявленные ошибки исправлены.

> 🛠 [Валидатор CSS](https://jigsaw.w3.org/css-validator/)

* [ ] **Направление чтения:** ![Высокий][high_img] Все страницы должны быть протестированы для языков с направлением чтения слева направо (LTR) и справа налево (RTL), если необходима поддержка этих языков.

> * 📖 [Building RTL-Aware Web Apps & Websites: Part 1 | Mozilla Hacks](https://hacks.mozilla.org/2015/09/building-rtl-aware-web-apps-and-websites-part-1/)
> * 📖 [Building RTL-Aware Web Apps & Websites: Part 2 | Mozilla Hacks](https://hacks.mozilla.org/2015/10/building-rtl-aware-web-apps-websites-part-2/)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Изображения

> **Примечание:** Для полного понимания оптимизации изображений советую эту бесплатную электронную книгу — **[Essential Image Optimization](https://images.guide/)** авторства Addy Osmani.

### Лучшие практики

* [ ] **Оптимизация:** ![Высокий][high_img] Все изображения должны быть оптимизированы для отображения в браузере. Для ключевых страниц сайта (таких, как главная страница) можно использовать формат WebP.

> * 🛠 [Imagemin](https://github.com/imagemin/imagemin)
> * 🛠 Используйте бесплатный инструмент [ImageOptim](https://imageoptim.com/) для оптимизации изображений.

* [ ] **Retina:** ![Низкий][low_img] Предусмотрены изображения в увеличенном разрешении x2 или 3x для поддержки Retina-дисплеев.
* [ ] **Спрайты:** ![Средний][medium_img] Маленькие изображения собраны в спрайт (иконки могут быть SVG-спрайтом).
* [ ] **Ширина и высота:** ![Высокий][high_img] Для всех тегов `<img>` установлена ширина и высота (без указания px или %).

> ***Примечание:*** Многие разработчики считают, что использование ширины и высоты несовместимо с адаптивным веб-дизайном. Это абсолютно не так.

* [ ] **Альтернативный текст:** ![Высокий][high_img] У всех тегов `<img>` есть альтернативный текст, описывающий изображение.
* [ ] **Ленивая загрузка (Lazy loading):** ![Средний][medium_img] Изображения используют «ленивую» отложенную загрузку (но обязательно нужно предусмотреть резервный вариант отображения на тот случай, если в браузере отключен JS).

**[⬆ обратно к содержанию](#table-of-contents)**

---

## JavaScript

### Лучшие практики

* [ ] **Инлайновый JavaScript:** ![Высокий][high_img] Нет инлайнового JavaScript-кода (смешанного с HTML-кодом).
* [ ] **Объединение JS-файлов:** ![Высокий][high_img] JS-файлы объединены.
* [ ] **Минификация:** ![Высокий][high_img] JS-файлы минифицированы (можно добавить к названию файла суффикс `.min`).

> [Сократите объем ресурсов (HTML, CSS и JavaScript)](https://developers.google.com/speed/docs/insights/MinifyResources)

* [ ] **Безопасность JavaScript:**

> [Guidelines for Developing Secure Applications Utilizing JavaScript](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet#Guidelines_for_Developing_Secure_Applications_Utilizing_JavaScript)*

* [ ] **Неблокирующий JS:** ![Средний][medium_img] JavaScript-файлы загружаются асинхронно, с использованием `async`, либо отложенно, с использованием атрибута `defer`.

> 📖 [Удалите JavaScript-код, препятствующий показу страницы](https://developers.google.com/speed/docs/insights/BlockingJS)

* [ ] **Modernizr:** ![Низкий][low_img] Чтобы проверить поддержку той или иной технологии в браузере, можно настроить и использовать библиотеку Modernizr. Modernizr проведет тесты и добавит соответствующие классы в тег `<html>` в зависимости от браузера, позволяя «откатить» функции для старых версий браузеров.

> 🛠 [Customize your Modernizr](https://modernizr.com/download?setclasses)

### Тестирование JavaScript

* [ ] **ESLint:** ![Высокий][high_img] ESLint не должен обнаружить никаких ошибок (на основании ваших настроек или стандартных правил).

> * 📖 [ESLint - The pluggable linting utility for JavaScript and JSX](https://eslint.org/)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Безопасность

### Проверьте безопасность вашего сайта

> * [securityheaders.io](https://securityheaders.io/)
> * [Observatory от Mozilla](https://observatory.mozilla.org/)
> * [ASafaWeb - Automated Security Analyser for ASP.NET Websites](https://asafaweb.com/)

### Лучшие практики

* [ ] **HTTPS:** ![Средний][medium_img] HTTPS используется на всех страницах и для всего внешнего содержимого (плагины, изображения и т.д.).

> * 🛠 [Let's Encrypt - Free SSL/TLS Certificates](https://letsencrypt.org/)
> * 🛠 [Free SSL Server Test](https://www.ssllabs.com/ssltest/index.html)
> * 📖 [Strict Transport Security](http://caniuse.com/#feat=stricttransportsecurity)

* [ ] **HTTP Strict Transport Security (HSTS):** ![Средний][medium_img] Используется HTTP-заголовок 'Strict-Transport-Security'.

> * 🛠 [Check HSTS preload status and eligibility](https://hstspreload.org/)
> * 📖 [HTTP Strict Transport Security Cheat Sheet - OWASP](https://www.owasp.org/index.php/HTTP_Strict_Transport_Security_Cheat_Sheet)
> * 📖 [Transport Layer Protection Cheat Sheet - OWASP](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet)

* [ ] **Межсайтовая подделка запроса — Cross Site Request Forgery (CSRF):** ![Высокий][high_img] Убедитесь, что запросы к серверу не являются нежелательными и отправляются с вашего сайта/приложения, чтобы исключить возможность CSRF-атак.

> 📖 [Cross-Site Request Forgery (CSRF) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet)

* [ ] **Межсайтовый скриптинг — Cross Site Scripting (XSS):** ![Высокий][high_img] Ваш сайт/веб-страница защищена от возможных XSS-атак.

> * 📖 [XSS (Cross Site Scripting) Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet)
> * 📖 [DOM based XSS Prevention Cheat Sheet  - OWASP](https://www.owasp.org/index.php/DOM_based_XSS_Prevention_Cheat_Sheet)

* [ ] **Заголовок Content Type Options** ![Средний][medium_img] Предотвращает попытки Google Chrome и Internet Explorer использовать MIME-сниффер для определения типа содержимого ответа, отличающегося от типов, передаваемых сервером.

> * 📖 [X-Content-Type-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-content-type-options)

* [ ] **Заголовок X-Frame-Options (XFO)** ![Средний][medium_img] Защищает пользователей от кликджекинг-атак.

> * 📖 [X-Frame-Options - Scott Helme](https://scotthelme.co.uk/hardening-your-http-response-headers/#x-frame-options)
> * 📖 [RFC7034 - HTTP Header Field X-Frame-Options](https://tools.ietf.org/html/rfc7034)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Производительность

### Лучшие практики

- [ ] **Размер страниц:** ![Высокий][high_img] Размер каждой из страниц сайта — от 0 до 500 KB.

> * 🛠 [Website Page Analysis](https://tools.pingdom.com)
> * 📖 [Size Limit: Make the Web lighter](https://evilmartians.com/chronicles/size-limit-make-the-web-lighter)

- [ ] **Минификация HTML:** ![Средний][medium_img] HTML-код минифицирован.
> 🛠 [Валидатор W3C](https://validator.w3.org/)

* [ ] **Ленивая загрузка (lazy loading):** ![Средний][medium_img] Изображения, скрипты и CSS используют «ленивую» загрузку для уменьшения времени загрузки страницы (подробности — в соответствующих разделах).

* [ ] **Размер куки:** Если вы используете куки, убедитесь, что размер каждого куки не превышает 4096 байт, и от одного домена установлено не более 20 куков.

> * 📖 [Cookie specification: RFC 6265](https://tools.ietf.org/html/rfc6265)
> * 📖 [Куки HTTP](https://developer.mozilla.org/ru/docs/Web/HTTP/Куки)
> * 🛠 [Browser Cookie Limits](http://browsercookielimits.squawky.net/)

### Preparing upcoming requests

> 📖 [Explanation of the following techniques](https://css-tricks.com/prefetching-preloading-prebrowsing/)

* [ ] **Разрешение DNS-имен, атрибут `prefetch`** ![Низкий][low_img] Доменные имена сторонних ресурсов, которые могут понадобится, загружаются заранее с помощью `dns-prefetch`.

```html
<link rel="dns-prefetch" href="https://example.com">
```

* [ ] **Атрибут `preconnect`:** ![Низкий][low_img] DNS-запрос, рукопожатие TCP и согласование TLS с ресурсами, которые вскоре понадобятся, загружаются заранее с помощью `preconnect`.

```html
<link rel="preconnect" href="https://example.com">
```

* [ ] **Атрибут `prefetch`:** ![Низкий][low_img] Ресурсы, которые вскоре понадобятся (такие как изображения, использующие ленивую загрузку), запрашиваются заранее с использованием `prefetch`.

```html
<link rel="prefetch" href="image.png">
```

* [ ] **Предзагрузка, атрибут `preload`:** ![Низкий][low_img] Ресурсы, необходимые на данной странице (такие как скрипты, размещенные перед закрывающим `</body>`), загружаются заранее с помощью `preload`.

```html
<link rel="preload" href="app.js">
```

> 📖 [Разница между prefetch и preload (англ.)](https://medium.com/reloading/preload-prefetch-and-priorities-in-chrome-776165961bbf)

### Тестирование производительности

* [ ] **Google PageSpeed:** ![Высокий][high_img] Все страницы протестированы с помощью Google PageSpeed Insights (не только главная страница) и имеют показатель не менее 90/100.

> * 🛠 [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
> * 🛠 [Test your mobile speed with Google](https://testmysite.withgoogle.com)
> * 🛠 [WebPagetest - Website Performance and Optimization Test](https://www.webpagetest.org/)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Доступность

> **Примечание:** Посмотрите видео из плейлиста [A11ycasts with Rob Dodson](https://www.youtube.com/playlist?list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g) 📹

### Лучшие практики

- [ ] **Прогрессивное улучшение:** ![Средний][medium_img] Основные функции, такие как основная навигация и поиск, должны работать без включенного JavaScript.

> 📖 [Enable / Disable JavaScript in Chrome Developer Tools](https://www.youtube.com/watch?v=kBmvq2cE0D8)

- [ ] **Цветовой контраст:** ![Средний][medium_img] Цветовой контраст должен как минимум соотвествовать уровню AA стандарта WCAG (для мобильных устройств — уровню AAA).

> 🛠 [Контрастность](https://leaverou.github.io/contrast-ratio/)

#### Заголовки

* [ ] **Заголовок `h1`:** ![Высокий][high_img] Все страницы должны иметь заголовок `h1`, не являющийся названием сайта.
* [ ] **Заголовки:** ![Высокий][high_img] Заголовки должны использоваться надлежащим образом в правильном порядке (от `h1` до `h6`).

> 📹 [Why headings and landmarks are so important — A11ycasts #18](https://www.youtube.com/watch?v=vAAzdi1xuUY&index=9&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

#### Роли-ориентиры (ARIA Landmarks) — атрибут `role`

- [ ] **Роль `banner`:** ![Высокий][high_img] У тега `<header>` атрибут `role` имеет значение `role="banner"`.
- [ ] **Роль `navigation`:** ![Высокий][high_img] У тега `<nav>` атрибут `role` имеет значение `role="navigation"`.
- [ ] **Роль `main`:** ![Высокий][high_img] У тега `<main>` атрибут `role` имеет значение `role="main"`.

> 📖 [Using ARIA landmarks to identify regions of a page](https://www.w3.org/WAI/GL/wiki/Using_ARIA_landmarks_to_identify_regions_of_a_page)

### Семантика

- [ ] **Используются специальные типы ввода HTML5:** ![Средний][medium_img] Это особенно важно для мобильных устройств, которые показывают различные клавиатуры и виджеты для разных типов ввода.

> 📖 [Mobile Input Types](http://mobileinputtypes.com/)

### Формы

* [ ] **Метки (`label`):** ![Высокий][high_img] Метка `label` связана с каждым элементом `input` формы. Если метка не может быть отображена, используйте вместо нее атрибут `aria-label`.

> 📖 [Using the aria-label attribute - MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute)

### Проверка доступности

* [ ] **Проверка стандартов доступности:** ![Высокий][high_img] Используйте инструмент WAVE (Web Accessibility Evaluation Tool), чтобы протестировать, соответствует ли страница стандартам доступности.

> 🛠 [Wave testing](http://wave.webaim.org/)

* [ ] **Навигация с клавиатуры:** ![Высокий][high_img] Протестируйте сайт используя для навигации только клавиатуру. Все интерактивные элементы должны быть доступны и пригодны для использования.
* [ ] **Скринридеры:** ![Средний][medium_img] Все страницы протестированы в скринридере (VoiceOver, ChromeVox, NVDA или Lynx).
* [ ] **Стиль фокуса:** ![Высокий][high_img] Если стандартный фокус отключен, вместо этого он должен быть стилизован через CSS.

> 📹 [Managing Focus - A11ycasts #22](https://www.youtube.com/watch?v=srLRSQg6Jgg&index=5&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## SEO

* [ ] **Google Analytics:** ![Высокий][high_img] Счетчик Google Analytics установлен и правилньно настроен.
* [ ] **Логика заголовков:** ![Средний][medium_img] Текст заголовка помогает понять содержимое данной страницы.
* [ ] **sitemap.xml:** ![Высокий][high_img] Файл sitemap.xml существует и представлен в Google Search Console (ранее Google Webmaster Tools).
* [ ] **robots.txt:** ![Высокий][high_img] Файл robots.txt не блокирует страницы сайта.

> * 🛠 Проверьте robots.txt с помощью инструмента [Google Robots Testing Tool](https://www.google.com/webmasters/tools/robots-testing-tool)

* [ ] **Структурированные данные:** ![Высокий][high_img] Страницы, использующие структурированные данные, протестированы и ошибок не обнаружено. Структурированные данные помогают поисковым роботам понимать содержимое страницы.

> * 📖 [Introduction to Structured Data | Search | Google Developers](https://developers.google.com/search/docs/guides/intro-structured-data)
> * 🛠 Протестируйте вашу страницу с помощью этого [инструмента проверки структурированных данных](https://developers.google.com/structured-data/testing-tool/)

* [ ] **HTML-карта сайта:** ![Средний][medium_img] HTML-карта сайта существует и доступна по ссылке в футере сайта.

> * 📖 [Как создавать и отправлять файлы Sitemap | Google Support](https://support.google.com/webmasters/answer/183668?hl=ru)
> * 🛠 [Генератор карты сайта](https://websiteseochecker.com/html-sitemap-generator/)


**[⬆ обратно к содержанию](#table-of-contents)**

---

## Перевод

Чек-лист фронтенда также доступен на других языках. Спасибо всем переводчикам за их замечательную работу!

* 🇯🇵 Japanese: [miya0001/Front-End-Checklist](https://github.com/miya0001/Front-End-Checklist)

* ru Russian: [missis-sippi/Front-End-Checklist](https://github.com/missis-sippi/Front-End-Checklist)

**[⬆ обратно к содержанию](#table-of-contents)**

---

## Вклад

**Откройте issue или pull request, чтобы предложить изменения или дополнения.**

### Инструкция

Репозиторий *Чек-листа фронтенда** имеет две ветки:

#### 1. `master`

Эта ветка содержит файл `README.md`, который автоматически отображается на сайте [Front-End Checklist](http://frontendchecklist.com/).

#### 2. `develop`

Эта ветка будет использоваться для внесения существенных изменений в структуру и содержимое в случае необходимости. Для исправления небольших ошибок и добавления новых пунктов лучше использовать ветку `master`.

### Соавторы

Вот список всех наших чудесных [соавторов](https://github.com/thedaviddias/frontendchecklist/graphs/contributors).

## Авторы

**[David Dias](https://github.com/thedaviddias/Front-End-Checklist)**, **[Geoffrey Signorato](https://github.com/geosenna)**, **[Sandeep Ramgolam](https://twitter.com/__Sun__)** and **[Cédric Poilly](https://github.com/CedricPoilly)**.

## Лицензия

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ обратно к содержанию](#table-of-contents)**

[low_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-low.png
[medium_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-medium.png
[high_img]: http://res.cloudinary.com/djnyaloac/image/upload/v1508238836/level-checklist-high.png

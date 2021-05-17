# [Twitter Cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/guides/getting-started)

Twitter card tags look similar to Open Graph tags, and are based on the same conventions as the Open Graph protocol. When using Open Graph protocol to describe data on a page, it is easy to generate a Twitter card without duplicating tags and data. When the Twitter card processor looks for tags on a page, it first checks for the Twitter-specific property, and if not present, falls back to the supported Open Graph property. This allows for both to be defined on the page independently, and minimizes the amount of duplicate markup required to describe content and experience.

Note that while Open Graph recommends specifying the “og” RDFa Core 1.1 CURIE prefix mapping via <html prefix="og: http://ogp.me/ns#">, no such markup is required for Twitter cards and its use of the twitter: prefix in a HTML meta element’s name attribute. Open Graph protocol also specifies the use of property and content attributes for markup (<meta property="og:image" content="http://example.com/ogp.jpg"/>) while Twitter cards use name and content. Twitter’s parser will fall back to using property and content, so there is no need to modify existing Open Graph protocol markup if it already exists.

The example below uses a mix of Twitter and Open Graph tags to define a summary card:

```html
<meta name="twitter:card" content="summary" />
<meta name="twitter:site" content="@nytimesbits" />
<meta name="twitter:creator" content="@nickbilton" />
<meta property="og:url" content="http://bits.blogs.nytimes.com/2011/12/08/a-twitter-for-my-sister/" />
<meta property="og:title" content="A Twitter for My Sister" />
<meta property="og:description" content="In the early days, Twitter grew so quickly that it was almost impossible to add new features because engineers spent their time trying to keep the rocket ship from stalling." />
<meta property="og:image" content="http://graphics8.nytimes.com/images/2011/12/08/technology/bits-newtwitter/bits-newtwitter-tmagArticle.jpg" />
```


# [Open Graph](https://ruogp.me/) og:tag
## Основные теги
- `og:title` - Название вашего объекта, как он должен отображаться
- `og:type` - [Тип объектa](https://ruogp.me/#types)
- `og:image` - URL-адрес изображения, который должен определить Ваш объект в графе для изображения
- `og:url` - Канонический URL-адрес объекта, который будет использоваться в качестве его постоянного ID в графе

```html
<meta property="og:title" content="Мэрилин Монро"/>
<meta property="og:description" content="Американская киноактриса и певица"/>
<meta property="og:image" content="https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/Marilyn_Monroe_-_publicity.JPG/210px-Marilyn_Monroe_-_publicity.JPG"/>
<meta property="og:type" content="profile"/>
<meta property="og:url" content= "https://ru.wikipedia.org/wiki/Мэрилин_Монро" />
```

## Дополнительные теги
- `og:audio` — URL звукового файла, который относится к описываемому объекту.
- `og:description` - Одно-два предложения описания вашего объекта.
- `og:locale` - Тег локации. Формат language_TERRITORY. По умолчанию en_US.
- `og:locale:alternate` - Тип array других локалей на этой странице.
- `og:site_name` - Если ваш объект является частью большого web-сайта, название, должно отображаться на всех страницах сайта. Например, "IMDb".
- `og:determiner` - Слово, которое появляется перед названием этого объекта в предложении. Тип enum (a, an, the, "", auto). Если выбрано auto, потребитель данных должен выбирать между "a" или "an". По умолчанию - " " (пусто).
- `og:video` - URL-адрес видео-файла, который сопутствует этому объекту.

```html
<meta property="og:audio" content="http://example.com/bond/theme.mp3" />
<meta property="og:description" content="Sean Connery found fame and fortune as the suave, sophisticated British agent, James Bond." />
<meta property="og:determiner" content="the" />
<meta property="og:locale" content="en_GB" />
<meta property="og:locale:alternate" content="fr_FR" />
<meta property="og:locale:alternate" content="es_ES" />
<meta property="og:site_name" content="IMDb" />
<meta property="og:video" content="http://example.com/bond/trailer.swf" />
```

Свойство тега og:image имеет несколько дополнительных структурированных свойств:

- `og:image:url` - Идентичный `og:image`.
- `og:image:secure_url` - Альтернативный url-адрес для использования в случае, если web-страница требует HTTPS.
- `og:image:type` - Типы MIME для изображения.
- `og:image:width` - Число пикселей в ширину.
- `og:image:height` - Число пикселей в высоту.

```html
<meta property="og:image" content="http://example.com/ogp.jpg" />
<meta property="og:image:secure_url" content="https://secure.example.com/ogp.jpg" />
<meta property="og:image:type" content="image/jpeg" />
<meta property="og:image:width" content="400" />
<meta property="og:image:height" content="300" />
```

Свойство тега `og:video` имеет идентичные теги с `og:image`.

Тег `og:audio` имеет только 3 доступных свойства (`og:audio`, `og:audio:secure_url`, `og:audio:type`)

Если тег может иметь несколько значений, просто поставьте несколько таких тегов ``<meta>`` на вашей странице. Приоритет тегам отдается с верху вниз, при возникновении конфликтов.

```html
<meta property="og:image" content="http://example.com/rock.jpg" />
<meta property="og:image" content="http://example.com/rock2.jpg" />
```

# [apple-touch-icon](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

- `apple-touch-icon-precomposed` - иконки с заранее наложенными эффектами в стиле iOS.
- `apple-touch-icon` - иконки без эффектов, мобильное устройство само наложит на эту иконку свои эффекты.
    - Rounded corners
    - Drop shadow
    - Reflective shine

```html
<!-- For Chrome for Android: -->
<link rel="icon" sizes="192x192" href="touch-icon-192x192.png">
<!-- For iPhone 6 Plus with @3× display: -->
<link rel="apple-touch-icon-precomposed" sizes="180x180" href="apple-touch-icon-180x180-precomposed.png">
<!-- For iPad with @2× display running iOS ≥ 7: -->
<link rel="apple-touch-icon-precomposed" sizes="152x152" href="apple-touch-icon-152x152-precomposed.png">
<!-- For iPad with @2× display running iOS ≤ 6: -->
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="apple-touch-icon-144x144-precomposed.png">
<!-- For iPhone with @2× display running iOS ≥ 7: -->
<link rel="apple-touch-icon-precomposed" sizes="120x120" href="apple-touch-icon-120x120-precomposed.png">
<!-- For iPhone with @2× display running iOS ≤ 6: -->
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="apple-touch-icon-114x114-precomposed.png">
<!-- For the iPad mini and the first- and second-generation iPad (@1× display) on iOS ≥ 7: -->
<link rel="apple-touch-icon-precomposed" sizes="76x76" href="apple-touch-icon-76x76-precomposed.png">
<!-- For the iPad mini and the first- and second-generation iPad (@1× display) on iOS ≤ 6: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="apple-touch-icon-72x72-precomposed.png">
<!-- For non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon-precomposed" href="apple-touch-icon-precomposed.png"><!-- 57×57px -->
```

- `apple-touch-icon-57x57-precomposed.png` or `apple-touch-icon-57x57.png` for non-Retina iPhone and iPod Touch (@1× display);
- `apple-touch-icon-76x76-precomposed.png` or `apple-touch-icon-76x76.png` for the iPad mini and the first- and second-generation iPad (@1× display) on iOS ≥ 7;
- `apple-touch-icon-120x120-precomposed.png` or `apple-touch-icon-120x120.png` for iPhone 4+ (with @2× display) on iOS ≥ 7;
- `apple-touch-icon-152x152-precomposed.png` or `apple-touch-icon-152x152.png` for iPad 3+ (with @2× display);
- `apple-touch-icon-180x180-precomposed.png` or `apple-touch-icon-180x180.png` for iPhone 6 Plus (with @3× display);
- `touch-icon-192x192.png` for Chrome for Android;
- `apple-touch-icon-precomposed.png` and `apple-touch-icon.png` as a fallback for everything else (possibly including non-Apple devices).

[Everything you always wanted to know about touch icons · Mathias Bynens](https://mathiasbynens.be/notes/touch-icons)
# [manifest.json](https://developer.mozilla.org/en-US/docs/Web/Manifest)

# [browserconfig.xml](https://msdn.microsoft.com/en-us/library/ie/dn455106.aspx)

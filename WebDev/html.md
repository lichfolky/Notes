# html
```
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

## <head> element
This includes keywords, page description

- Add CSS file
  `<link rel="stylesheet" href="my-css-file.css">`
- Add javascript file
  `<script src="my-js-file.js" defer></script>`
  `defer` makes sure that the HTML is all loaded before the JavaScript runs
- character set declaration
  `<meta charset="utf-8">`
- favicon (16-pixel square image: .ico, .gif, .png) (IE6 only .ico)
  `<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">`
  - thers favicons
    ```
    <!-- third-generation iPad with high-resolution Retina display: -->
    <link rel="apple-touch-icon-precomposed" sizes="144x144" href="...png">
    <!-- iPhone with high-resolution Retina display: -->
    <link rel="apple-touch-icon-precomposed" sizes="114x114" href="...png">
    <!-- first- and second-generation iPad: -->
    <link rel="apple-touch-icon-precomposed" sizes="72x72" href="...png">
    <!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
    <link rel="apple-touch-icon-precomposed" href="...png">
    <!-- basic favicon -->
    <link rel="shortcut icon" href="...png">
    ```
- `<title>`
  - use different titles for each page!
  - It's the text in the favorite page name **SEO**
- page language
  `<html lang="en-US">`
  - for subsections: `<p>Japanese example: <span lang="ja">ご飯が熱い。</span>.</p>`
- Others:
  - '-' in files are treated by google as word separators, _ not. **SEO**
## site structure
- header: <header>.
<header> represents a group of introductory content. If it is a child of <body> it defines the global header of a webpage, but if it's a child of an <article> or <section> it defines a specific header for that section (try not to confuse this with titles and headings).
- navigation bar: <nav>.
- main content: <main>, with various content subsections represented by <article>, <section>, and <div> elements.
- sidebar: <aside>; often placed inside <main>.
- footer: <footer>.

## keywords **SEO**
```
<meta name="author" content="Chris Mills">
```
- sitelinks, and are configurable in Google's webmaster tools **SEO**
  - `<meta name="keywords" ...>` it's not used anymore
- Open Graph Data (Facebook post)**SEO**
  ```
  <meta property="og:title" content="Mozilla Developer Network">
  ```
- Twitter Cards**SEO**
  ```
  <meta name="twitter:title" content="Mozilla Developer Network">
  ```

## text style

- `<am>` italic
- `<strong>` bold
- `<p>` you can't put inside a div
- `<h1>` use headings for structure web page, not for style. **SEO**
  - Preferably, you should use a single <h1> per page
  - Correct order in the hierarchy <h1> -> <h2> -> <h3>
  - More than 3 is too much
- `<button> `it's better to use a button and change its style than using a div
- don't use `<b>`, `<i>`, and `<u>`

## lists
- Unordered lists:
  ```
  <ul>
    <li>milk</li>
    <li>eggs</li>
  </ul>
  ```
  - with style none you delete points
- Ordered lists:
  ```
  <ol>
    <li>milk</li>
    <li>eggs</li>
  </ol>
  ```
- You can nest them!
- Description lists
  ```
  <dl>
    <dt>aside</dt>
    <dd>In drama, where a character shares a comment only with the audience for humorous or dramatic effect. This is usually a feeling, thought, or piece of additional background information.</dd>
    <dd>In writing, a section of content that is related to the current topic, but doesn't fit directly into the main flow of content so is presented nearby (often in a box off to the side.)</dd>
  </dl>
  ```

# Links
```
we should visit <a href="https://www.mozilla.org/en-US/"
title="The best site in the web">the Mozilla homepage</a>.
```
- title it's revealed on mouse hover
- it's better to use in a word of a sentence than using in a generic "read more"
  es "click here" to download the img -> "download the img"
- Almost any content can be made into a link, even block-level elements.
  ```
  <a href="https://www.mozilla.org/en-US/">
    <img src="mozilla-image.png" alt="mozilla logo that links to the mozilla homepage">
  </a>
  ```
- for local files:
  ```
  <a href="contacts.html">
  <a href="projects/index.html">
  <a href="../pdfs/project-brief.pdf">
  ```  
- document fragments
  ```  
  <a href="contacts.html#Mailing_address">
  where contacts.html contains
  ...
  <h2 id="Mailing_address">Mailing address</h2>
  ...
  in the same page:
  <a href="#Mailing_address">
  ```  
- Use relative links wherever possible
- Download links:
  ```
  <a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
   download="firefox-latest-64bit-installer.exe">
  Download Latest Firefox for Windows (64-bit) (English, US)
  </a>
  ```
- Email links:
  ```
  <a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
    Send mail with cc, bcc, subject and body
  </a>
  ```

## special char
```
<	&lt;
>	&gt;
"	&quot;
'	&apos;
&	&amp;
```

## Others
<blockquote>
<cite>
The quote element:
<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended
for short quotations that don't require paragraph breaks.</q></p>

<address>

- x power of 2 : x<sup>2</sup>
- x element j : x<sub>j</sub>

<code> for code
<pre>: For retaining whitespace (generally code blocks)

<time datetime="2016-01-20">20 January 2016</time>


# attributes
alt use it! **SEO**
# Other
- HTML parser reduces each sequence of whitespace to a single space
- comments : <!-- COMMENT -->

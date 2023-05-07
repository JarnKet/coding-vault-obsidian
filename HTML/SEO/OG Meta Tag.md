


---
banner: "https://www.elegantthemes.com/blog/wp-content/uploads/2023/02/google-preview.jpg"
tag: SEO, HTML
---
Source: https://ogp.me

> [!abstract] 
> Open Graph Meta Tag ແມ່ນເປັນຊຸດຄຳສັ່ງໃນການຄວບຄຸມການສະແດງຜົນຂອງ URL ເມື່ອມີການ Share ໄປທີ່ແພັດຟອມ Social Media. 
> OG Meta Tag ແມ່ນເປັນສ່ວນໜຶ່ງຂອງ Facebook ແລະ ຍັງຖືກໃຊ້ໂດຍແອັບອື່ນໆເຊັ່ນ: LinkedIn ແລະ Twitter.

> [!hint] 
> ເຮົາສາມາດນຳໃຊ້າພາຍໃນ `<head>` ແລະ ໃຊ້ດ້ວຍ `<meta>` ທີ່ພາຍໃນກຳນົດດ້ວຍ `property='og:...'` 

**ຕົວຢ່າງການໃຊ້ງານ**

``` HTML
<meta property="og:title" content="How to Become an SEO Expert (8 Steps)" />
<meta property="og:description" content="Get from SEO newbie to SEO pro in 8 simple steps." />
<meta property="og:image" content="https://ahrefs.com/blog/wp-content/uploads/2019/12/fb-how-to-become-an-seo-expert.png" />

```

**ຕົວຢ່າງເນື້ອຫາທີ່ຜ່ານການໃຊ້ OG Meta Tag**

![[Pasted image 20230506204522.png]]

## ເປັນຫຍັງ OG Meta Tag ຈິ່ງສຳຄັນ

ປົກກະຕິແລ້ວຄົນສ່ວນໃຫ່ຍມັກທີ່ຈະເຫັນ ແລະ ແຊເນື້ອຫາທີ່ມີການໃຊ້ OG Tags ເພາະວ່າສາມາດເຫັນຈຸດປະສົງຂອງເນື້ອຫານັ້ນໆໂດຍກົງ ແລະ ກໍ່ໝາຍຄວາມວ່າ ເວັບໄຊທ໌ຂອງເຮົາກໍ່ ສາມາດມີປະຕິສຳພັນກັບ Social Media.

ການນຳໃຊ້ Meta Tag ມີຜົນດີດັ່ງນີ້:

1. ພວກເຂົາສາມາດເຫັນເນື້ອຫາຂອງພວກເຮົາໄດ້ງ່າຍ ໃນໜ້າ Feed.
2. ສາມາດຊ່ວຍໃຫ້ຜູ້ຄົນເຫັນເຖິງເນື້ອໃນໃຈຄວາມຂອງ ເນື້ອຫາເຮົາໄດ້.
3. ຊ່ວຍໃຫ້ Facebook ແລະ Social Media ແພັດຟອມອື່ໜທ ສາມາດເຂົ້າໃຈໄດ້ວ່າເນື້ອຫານີ້ເປັນແບບໃດ ແລະ ຊ່ວຍໃຫ້ເນື້ອຫາຂອງເຮົາສາມາດເຂົ້າເຖິງຜູ້ໃຊ້ໄດ້ງ່າຍ

![[Pasted image 20230506210636.png]]

## Which Open Graph tags should you use?

Facebook lists 17 OG tags in their [official documentation](https://developers.facebook.com/docs/sharing/webmasters/), plus dozens of object types. We’re not going to discuss all of these. Only four are required for Facebook to understand the basics of your page, and there are a couple of others that sometimes help.

Let’s go through these.

### og:title

The title of your page.

#### Syntax

``` HTML
<meta property="og:title" content="Open Graph Meta Tags: Everything You Need to Know" />
```

#### Best practices

-   Add it to all “shareable” pages.
-   Focus on accuracy, value, and clickability.
-   Keep it short to prevent overflow. There’s no official guidance on this, but 40 characters for mobile and 60 for desktop is roughly the sweet spot.
-   Use the raw title. Don’t include branding (e.g., your site name).

### og:url

The URL of the content.

#### Syntax

``` HTML
<meta property="og:url" content="https://ahrefs.com/blog/open-graph-meta-tags/" />
```

#### Best practices

-   Use the [canonical URL](https://ahrefs.com/blog/canonical-tags/). It helps consolidate all connected data, such as likes, across all the duplicate URLs posted.

### og:image

The URL of an image for the social snippet. 

Note that this is perhaps **the most essential Open Graph tag** because it occupies the most social feed real estate.

#### Syntax

``` HTML
<meta property="og:image" content="https://ahrefs.com/blog/wp-content/uploads/2020/01/fb-open-graph-1.jpg" />
```

#### Best practices

-   Use custom images for “shareable” pages (e.g., homepage, articles, etc.)
-   Use your logo or any other branded image for the rest of your pages.
-   Use images with a 1.91:1 ratio and [minimum recommended dimensions](https://developers.facebook.com/docs/sharing/webmasters/images) of 1200x630 for optimal clarity across all devices.

### og:type

The type of object you’re sharing. (e.g., article, website, etc.)

#### Syntax

``` HTML
<meta property="og:type" content="article" />
```

#### Best practices

-   Use [article](https://ogp.me/#type_article) for articles and [website](https://ogp.me/#type_website) for the rest of your pages.
-   Describe object types [further](https://ogp.me/#types) where appropriate (optional).

### og:description

A brief description of the content. 

#### Syntax

``` HTML
<meta property="og:description" content="Learn about 13 features that set Ahrefs apart from the competition." />
```

#### Best practices

-   Complement the title to make the snippet as appealing and click-worthy as possible.
-   Copy your meta description here if it makes sense. 
-   Keep it short and sweet. Facebook recommends 2-4 sentences, but that often truncates.

### og:locale

Defines the content language.

#### Syntax

``` HTML
<meta property="og:locale" content="en_GB" />
```

#### Best practices

-   Use only for content not written in American English (en_US). Facebook assumes content without this tag is written in this language.
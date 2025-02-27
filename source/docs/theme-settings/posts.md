---
title: Post Settings
description: NexT User Docs – Theme Settings – Posts
---

### Preamble Text

It's a common need to show some part of article in home page and then give a link to full article. NexT gives two ways to control how article is shown in home page. In other words, you can use following ways to show summary of articles and a **Read More** button.

{% tabs preamble %}
<!-- tab {% label success@Tag more %} -->
Use `<!-- more -->` in your article to break your article manually, which is recommended by Hexo.

<!-- endtab -->

<!-- tab <code>excerpt_description</code> -->
If you have added `description` and set its value to your article summary in [front-matter](https://hexo.io/docs/front-matter), NexT excerpts `description` as preamble text in homepage by default. Without `description`, the full contents would be the preamble text in homepage.

You can disable it by setting value `excerpt_description` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
excerpt_description: true
```

<!-- endtab -->
{% endtabs %}

{% note info %}
It is recommended to use `<!-- more -->` (the first way) which can not only control what you want to show better, but also let Hexo's plugins use it easily.
{% endnote %}

### Post Meta Display

NexT supports post created date, post updated date and post categories display.

{% tabs postmeta %}
<!-- tab <code>item_text</code> -->
By default NexT shows the description text of post meta. You can disable it by setting value `post_meta.item_text` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
post_meta:
  item_text: true
```
<!-- endtab -->

<!-- tab <code>created_at</code> -->
By default NexT shows the post created date in post meta section and created time in popup. You can disable it by setting value `post_meta.created_at` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
post_meta:
  created_at: true
```
<!-- endtab -->

<!-- tab <code>updated_at</code> -->

{% note warning %}
Make sure you set `use_date_for_updated` and `updated_option` in {% label info@site config file %} correctly, otherwise this option will not take effect. See also [Date / Time format](https://hexo.io/docs/configuration#Date-Time-format).
{% endnote %}

{% subtabs postmeta1 %}
<!-- tab <code>enable</code> -->
By default NexT shows the post updated date in post meta section and updated time in popup. You can disable it by setting value `post_meta.updated_at.enable` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
post_meta:
  updated_at:
    enable: true
```
<!-- endtab -->

<!-- tab <code>another_day</code> -->
By default, if updated/edited date is the same as created date, edited time would be displayed in popup message. You can disable it by setting value `post_meta.updated_at.another_day` to `false` in {% label primary@theme config file %}.
In other words:

* If true, show updated date label only if `updated date` is different from `created date` (post edited in another day than was created).
* And if post was edited in same day as created, edited time will show in popup title under created time label.
* If false show anyway, but if post edited in same day, show only edited time.

```yml next/_config.yml
post_meta:
  updated_at:
    another_day: true
```
<!-- endtab -->
{% endsubtabs %}

<!-- endtab -->

<!-- tab <code>categories</code> -->
By default NexT shows the post categorie in post meta section. You can disable it by setting value `post_meta.categories` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
post_meta:
  categories: true
```
<!-- endtab -->

{% endtabs %}

### Post Wordcount

{% tabs wordcount %}
<!-- tab Installation → -->
Install `hexo-word-counter` by executing the following command in {% label info@site root dir %}:

```bash
$ npm install hexo-word-counter
$ hexo clean
```
<!-- endtab -->

<!-- tab Hexo Config → -->
Activate this plugin in {% label info@site config file %} by enabled any option:

{% subtabs wordcount1 %}
<!-- tab <code>symbols</code> -->
By default NexT shows the number of post words in post meta section. You can disable it by setting value `symbols_count_time.symbols` to `false` in {% label info@site config file %}.

```yml hexo/_config.yml
symbols_count_time:
  symbols: true
```
<!-- endtab -->

<!-- tab <code>time</code> -->
By default NexT shows the estimated reading time of post in post meta section. You can disable it by setting value `symbols_count_time.time` to `false` in {% label info@site config file %}.

```yml hexo/_config.yml
symbols_count_time:
  time: true
```
<!-- endtab -->

<!-- tab <code>total_symbols</code> -->
By default NexT shows the number of all posts words in footer section. You can disable it by setting value `symbols_count_time.total_symbols` to `false` in {% label info@site config file %}.

```yml hexo/_config.yml
symbols_count_time:
  total_symbols: true
```
<!-- endtab -->

<!-- tab <code>total_time</code> -->
By default NexT shows the estimated reading time of all posts in footer section. You can disable it by setting value `symbols_count_time.total_time` to `false` in {% label info@site config file %}.

```yml hexo/_config.yml
symbols_count_time:
  total_time: true
```
<!-- endtab -->

<!-- tab <code>awl</code> -->
`awl` means the average Word Length (chars count in word). You can check this [here](https://charactercounttool.com/).

```yml next/_config.yml
symbols_count_time:
  awl: 4
```
<!-- endtab -->

<!-- tab <code>wpm</code> -->
`wpm` means the average words per minute. You can check this [here](https://wordcounter.net/).

```yml next/_config.yml
symbols_count_time:
  wpm: 275
```
<!-- endtab -->

{% endsubtabs %}

<!-- endtab -->

<!-- tab NexT Config -->
After the plugin enabled, you may adjust options in `symbols_count_time` section in {% label primary@theme config file %}:

{% subtabs wordcount2 %}
<!-- tab <code>separated_meta</code> -->
By default NexT shows the words counts and estimated reading time in a separated line. You can add them into one line by setting value `symbols_count_time.separated_meta` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
symbols_count_time:
  separated_meta: true
```
<!-- endtab -->

<!-- tab <code>item_text_total</code> -->
By default NexT doesn't shows the text description of the words counts and estimated reading time in footer section. You can enable it by setting value `symbols_count_time.item_text_total` to `false` in {% label primary@theme config file %}.

```yml next/_config.yml
symbols_count_time:
  item_text_total: true
```
<!-- endtab -->

{% endsubtabs %}

<!-- endtab -->
{% endtabs %}

### Tag Icon

By default, tags at the bottom of posts have a symbol # at there left side.

If you prefer icon instead of symbol, edit {% label primary@theme config file %} like following:

```yml next/_config.yml
tag_icon: true
```

### Donate Settings

More and more online blogging platforms (e.g. WeChat public accounts, Jianshu, Zhihu) support donate (sponsor). To catch paid reading trends, we added donate feature, supports WeChat, Alipay and Bitcoin. What you need is:

1. Get your WeChat / Alipay / Bitcoin receive money QRcode image(s) and put into `source/images` under {% label primary@theme directory %} or upload it(them) to an image cloud to get the absolute HTTP address(es).
2. Set needed values in  {% label primary@theme config file %}:

    ```yml next/_config.yml
    # Donate (Sponsor) settings
    # Front-matter variable (nonsupport animation).
    reward_settings:
      # If true, a donate button will be displayed in every article by default.
      enable: true
      animation: false
      #comment: Buy me a coffee

    reward:
      wechatpay: /images/wechatpay.png
      alipay: /images/alipay.png
      bitcoin: /images/bitcoin.png
    ```

You can also add QRcode of other platforms, e.g.

```yml next/_config.yml
paypal: /images/paypal.png
monero: /images/monero.png
```

### Follow Me

```yml next/_config.yml
# Subscribe through Telegram Channel, Twitter, etc.
# Usage: `Key: permalink || icon` (Font Awesome)
follow_me:
  #Twitter: https://twitter.com/username || fab fa-twitter
  #Telegram: https://t.me/channel_name || fab fa-telegram
  #WeChat: /images/wechat_channel.jpg || fab fa-weixin
  #RSS: /atom.xml || fa fa-rss
```

You can add links of other platforms not listed here, for example:

```yml next/_config.yml
follow_me:
  Zhihu: https://www.zhihu.com/people/username || fab fa-zhihu
```

### Related Popular Posts

NexT supports the related posts functionality according to [hexo-related-popular-posts](https://github.com/tea3/hexo-related-popular-posts).

{% tabs related_posts %}
<!-- tab Installation → -->
Install `hexo-related-popular-posts` by executing the following command in {% label info@site root dir %}:

```bash
$ npm install hexo-related-popular-posts
$ hexo clean
```
<!-- endtab -->

<!-- tab <code>enable</code> -->
You can enable it by setting value `related_posts.enable` to `true` in {% label primary@theme config file %}.

```yml next/_config.yml
related_posts:
  enable: true
```
<!-- endtab -->

<!-- tab <code>title</code> -->
By default NexT uses 'Related Posts' as title by default. You can configure it by editing value in `related_posts.title` section in {% label primary@theme config file %}.

```yml next/_config.yml
related_posts:
  title:
```
<!-- endtab -->

<!-- tab <code>display_in_home</code> -->
By default NexT doesn't show the related posts in homepage. You can enable it by setting value `related_posts.display_in_home` to `true` in {% label primary@theme config file %}.

```yml next/_config.yml
related_posts:
  display_in_home: true
```
<!-- endtab -->

<!-- tab <code>params</code> -->
By default NexT shows up to 5 related posts and their titles without any date, image and excerpt. You can change the default behavior by editing values of `related_posts.params` in {% label primary@theme config file %}.

{% subtabs related_posts1 %}
<!-- tab <code>maxCount</code> -->
Maximum count of a list, change it by yourself.

```yml next/_config.yml
related_posts:
  params:
    maxCount: 5
```
<!-- endtab -->

<!-- tab <code>PPMixingRate</code> -->
Mixing ratio of popular posts and related posts.

```yml next/_config.yml
related_posts:
  params:
    #PPMixingRate: 0.0
```
<!-- endtab -->

<!-- tab <code>isDate</code> -->
Uncomment and set true to display dates of related post.

```yml next/_config.yml
related_posts:
  params:
    isDate: true
```
<!-- endtab -->

<!-- tab <code>isImage</code> -->
Uncomment and set true to display images of related posts.

```yml next/_config.yml
related_posts:
  params:
    isImage: true
```
<!-- endtab -->

<!-- tab <code>isExcerpt</code> -->
Uncomment and set true to display excerpts of related posts.

```yml next/_config.yml
related_posts:
  params:
    isExcerpt: true
```
<!-- endtab -->

{% endsubtabs %}
<!-- endtab -->
{% endtabs %}

### Post Edit

NexT supports the edit functionality of your posts. By enabling this feature, users can quickly browse and modify the blog's source code on GitHub.

{% tabs post_edit %}
<!-- tab <code>enable</code> -->
You can enable it by setting value `post_edit.enable` to `true` in {% label primary@theme config file %}.

```yml next/_config.yml
post_edit:
  enable: true
```
<!-- endtab -->

<!-- tab <code>url</code> -->
You should create a source repository of your post files. The `url` setting depends on the source project in github.

* For site repository
  * Link for view source: `url: https://github.com/.../tree/master/source/_posts/`
  * Link for fork & edit: `url: https://github.com/.../edit/master/source/_posts/`
* For post repository
  * Link for view source: `url: https://github.com/.../_posts/tree/master/`
  * Link for fork & edit: `url: https://github.com/.../_posts/edit/master/`

```yml next/_config.yml
post_edit:
  url:
```
<!-- endtab -->

{% endtabs %}

### Post Navigation

Show previous post and next post in post footer if exists.

```yml next/_config.yml
post_navigation: left
```

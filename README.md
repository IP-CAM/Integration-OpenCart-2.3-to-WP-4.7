## OpenCart 2.3 и WP 4.7
The module uses WP REST API v2 for records and display them in the newswire OpenCart 2.3.x.  When used in conjunction with a plug WP Post To OpenCart possible to obtain directly from the WP positions and store them locally for further processing / display (see https://github.com/wlady/wp-post-to-opencart).

 After installation enter the correct address in the WP system / config / wp_post.php file.

 I used Twig templates to generate news feeds.  Example of a module All news:
```
<div class="row">
    <h3>Новости из WP</h3>
    {% for post in posts %}
            <div class="col-sm-6">
                    <a href="{{ post.link }}" class="blognews-item" target="_blank">
                        <img class="blognews-pic" src="{{ post.post_image.thumbnail.source_url }}" alt="" />
                        <span class="blognews-info">
                        <h4 class="blognews-title text-overflow">{{ post.title.rendered | raw }}</h4>
                        <span class="blognews-text">{{ post.excerpt.rendered | raw }}
                            <span class="blognews-more">... <i>read more</i></span>
                        </span>
                        <span class="blognews-detail">
                            <span class="blognews-date pull-right">{{ post.date }}</span>
                        </span>
                    </span>
                </a>
            </div>
    {% endfor %}
</div>
```


Для использования **Twig** в **OpenCart 2.3** достаточно установить необходимые пакеты с помощью _composer_:

```sh
composer require twig/twig --prefer-dist
```

![wordpress-0](wordpress-0.png)

![screenshot-0](screenshot-0.png)

![screenshot-1](screenshot-1.png)

![screenshot-2](screenshot-2.png)

![screenshot-3](screenshot-3.png)

![screenshot-4](screenshot-4.png)

![screenshot-5](screenshot-5.png)

![screenshot-6](screenshot-6.png)


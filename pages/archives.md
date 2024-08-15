---
layout: page
title: "Archives"
description: "冬无愆阳，夏无伏阴，春无凄风，秋无苦雨"
header-img: "img/archives-bg-dm.jpg"
---
<img src="https://ghchart.rshah.org/windleao"/>
<ul>
    {% for post in site.posts %}

    {% unless post.next %}
    <h2>{{ post.date | date: '%Y年' }}</h2>
    {% else %}
    {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
    {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
    {% if year != nyear %}
    <h2>{{ post.date | date: '%Y年' }}</h2>
    {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%Y年%m月%d日：" }} <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>
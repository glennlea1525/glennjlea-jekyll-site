---
layout: page
title: William Tyndale – Independent Thinker in the Lollard Tradition
permalink: /tyndale/home/
---

<div class="page-content-wrapper">
    <div class="plug">
        <div class="section-head">{{ page.title }}</div>
    
        <div class="section-description"><em>“If God spare my life, ere many yeares I wyl cause a boy that driveth the plough to know more of the Scripture, than he doust.” - Tyndale (as quoted by John Foxe).</em></div>
    </div>

    <div class="topic">

        <div class="article">
            <div class="article-body">
                <img class="post-image" src="{{ baseurl }}/assets/img/tyndale/tyndale-small.png" alt="Portrait of Michael Servetus">

                <p>Tyndale's contribution to the development of the English Bible is well known. His Theology is less so and these series of articles are an attempt to define in general terms his particular form of Christianity. Tyndale's theology is here seen as influenced by several movements, the first being Lollardy, the second Humanism, the third Lutheranism, and the fourth his own study of the Bible, particularly the Old Testament. From these influences Tyndale developed a unique theology, for which he suffered a heretic's death, but who nevertheless became a forerunner of the Separatist tradition in English religious history. These topics  examine the influences on his thought by Lollardy, Humanism, Lutheranism, and his own study.</p>

                <h1>Contents</h1>
                {% for item in site.data.tyndale.toc %}
                <ul>
            {% for entry in item.items %}
            <li><a href="{{ entry.url }}">{{ entry.title }}</a></li>
            {% endfor %}
        </ul>
        {% endfor %}
        </div>
    </div>
    </div>
</div>

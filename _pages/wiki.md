---
title: "Wiki"
layout: default
prefix-icon: "fas fa-book"
navigation_weight: 2
---

<script src="/assets/js/peekaboo.js"></script>

<h2 class="center">Frequently Viewed</h2>
<div class="two-grid">
    {% assign wiki_frequents = site.wiki | sort: 'frequent_weight' %}{% for wiki in wiki_frequents %}{% if wiki.ignore_listing != true %}{% if wiki.frequent == true %}{% if wiki.frequent_weight %}
    <div class="item{% if wiki.new %}{% else %} push-down{% endif %}">{% if wiki.new %}
        <h3 class="date">New in {{ wiki.new }}!</h3>{% endif %}
        <h3 class="title">{{ wiki.title }}</h3>
        <h5 class="subtitle">{{ wiki.tags }}</h5>
        <a class="bubble" href="{{ wiki.url }}" rel="noopener noreferrer">
            <img class="inner" src="/assets/docs/{{ wiki.image-path }}" alt="docs/{{ wiki.image-path }}"{% if wiki.peekaboo == true %} onmouseover="peekaboo(this);" onmouseout="unpeekaboo(this);"{% endif %}>
        </a>
        <p class="small">{{ wiki.description }}</p>
    </div>
    {% endif %}{% endif %}{% endif %}{% endfor %}
</div>

<h2 class="center">All Wikis</h2>
<div class="two-grid">
    {% assign wikis = site.wiki %}{% for wiki in wikis %}{% if wiki.ignore_listing != true %}
    <div class="item{% if wiki.new %}{% else %} push-down{% endif %}">{% if wiki.new %}
        <h3 class="date">New in {{ wiki.new }}!</h3>{% endif %}
        <h3 class="title">{{ wiki.title }}</h3>
        <h5 class="subtitle">{{ wiki.tags }}</h5>
        <a class="bubble" href="{{ wiki.url }}" rel="noopener noreferrer">
            <img class="inner" src="/assets/docs/{{ wiki.image-path }}" alt="docs/{{ wiki.image-path }}"{% if wiki.peekaboo == true %} onmouseover="peekaboo(this);" onmouseout="unpeekaboo(this);"{% endif %}>
        </a>
        <p class="small">{{ wiki.description }}</p>
    </div>{% endif %}{% endfor %}
</div>

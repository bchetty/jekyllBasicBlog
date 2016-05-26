---
layout: template1
title: Archive
comments: false
---

## Blog Posts by Category

<div class="panel-group" id="accordion">
    {% for category in site.categories %}
        <div class="panel panel-default">
            <div class="panel-heading">
                <h4 class="panel-title">
                    <a data-toggle="collapse" data-parent="#accordion" name="{{ category | first }}" href="#{{ category | first }}">
                        {{ category | first }}
                    </a>
                </h4>
            </div>
            
            <div id="{{ category | first }}" class="panel-collapse collapse in">
                <div class="panel-body">
                    <ul>
                        {% for posts in category %}
                            {% for post in posts %}
                                <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
                            {% endfor %}
                        {% endfor %}
                    </ul>
                </div>
            </div>
        </div>
    {% endfor %}
</div>


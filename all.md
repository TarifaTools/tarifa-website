---
layout: default
title: All Posts
permalink: /all/
---
{% include header.html %}
<section id="header" class="small">
    <div class="headline">
        <div class="wrapper">
            <h1>Your friendly toolchain for mobile app development <br><span>on top of Apache Cordova</span></h1>
        </div>
    </div>
</section>
<section id="blog">
    <div class="wrapper">
        <h3>All News</h3>
            <ul class="post-list">
                {% for post in site.posts %}
                <li><span class="post-meta"><span class="star">★ </span>{{ post.date | date: "%b %-d, %Y" }}</span><h4><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h4></li>
                {% endfor %}
                <li><a class="all-post-link" href="{{ "/feed.xml" | prepend: site.baseurl }}">Subscribe</a></li>
            </ul>
          </table>
    </div>
</section>

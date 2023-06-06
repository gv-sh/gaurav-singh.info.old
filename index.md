---
layout: layouts/default.njk
title: Gaurav Singh
subtitle:
---  

Profile: [Bio](/bio/), [OrcID](https://orcid.org/0000-0003-1651-6602), [Gh.](https://github.com/gv-sh), [Tw.](https://twitter.com/gvsh_maths) [Ig.](https://instagram.com/gvsh_maths)<br/>
Work: [Research](/research/), [Teaching](/teaching/)<br/>
Long term: [Mathscapes](/mathscapes/), [M56](/m56/)<br/>

[Send a message](https://bit.ly/contact-gaurav) 

<h2>Notes</h2>

<div>
    {%- for post in collections.post reversed -%}
    <div class="post">
        <img src="{{ post.data.cover }}" />
        <div>
            <p class="meta">{{ post.data.date | postDate }} / {{ post.data.category }} </p>
            <p><a href="{{ post.url}}">{{ post.data.title }}</a> {% if post.data.attrib %}<span class="meta">{{ post.data.attrib }}</span>{% endif %}</p>
        </div>
    </div>
    {%- endfor -%}
</div>
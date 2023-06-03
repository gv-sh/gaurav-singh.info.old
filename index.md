---
layout: layouts/default.njk
title: Gaurav Singh
subtitle: Researcher and Educator
---  
   
I am Gaurav, a researcher and educator from India, exploring the expansive realm of machine learning (ML) and human-computer interaction (HCI). My strong foundation in computer science, with an interest in visual arts, has helped me build a knack for image processing and complex data visualization, which I believe can be useful in my research. I am dedicated to advancing the field by approaching laterally, identifying hidden connections, and by making sophisticated data analysis techniques more accessible. In doing so, I am particularly interested in investigating the societal, environmental, and ethical implications within ML and HCI. [Learn more](/bio/)

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
---
layout: layouts/default.njk
title: Gaurav Singh
subtitle: Interdisciplinary researcher, HCI/ML
cover: https://cdn.mathscapes.xyz/static/images/2012.png
---  
   
I am Gaurav, a researcher and educator from India, exploring the expansive realm of machine learning (ML) and human-computer interaction (HCI). My strong foundation in computer science, with an interest in visual arts, has helped me build a knack for image processing and complex data visualization, which I believe can be useful in my research. I am dedicated to advancing the field by approaching laterally, identifying hidden connections, and by making sophisticated data analysis techniques more accessible. In doing so, I am particularly interested in investigating the societal, environmental, and ethical implications within ML and HCI. [Learn more](/about/)

<h2>Notes</h2>
  
<div>
    {%- for post in collections.post reversed -%}
    <div class="post">
        <img src="{{ post.data.cover }}" />
        <div>
            <p class="meta">{{ post.data.date | postDate }} / {{ post.data.category }} </p>
            <p><a href="{{ post.url}}">{{ post.data.title }}</a></p>
            {% if post.data.attrib %}<p class="meta">{{ post.data.attrib }}</p>{% endif %}
        </div>
    </div>
    {%- endfor -%}
</div>
  
Notes marked with [] are collaborative work. (+) indicates additional contribution from more people, including peers, mentors, or students. Names are sorted by first letter.
 
AS: Ashwin Senthil, AN: Anchit Shukla , AA: Apoorva Avadhana, AE: Anders Edelbo Lillie, AR: Aditi Rai, DB: Debanshu Bhaumik, DD: Daksha Dixit, MA: Mangesh Ashrit, NP: Nupur Patny, NB: Dr. Naveen Bagalkot, PD: Pratiksha Dixit, PO: Prakhar Ojha, RS: Riyaz Shaikh, SJ: Sarvashree Jain, SM: Shreya Mishra, SB: Suraj Baadkar, SO: Sowmya Saxena, SS: Simran Singh, SW: Swati Sharma, TS: Dr. Tomas Sokoler, VC: V Chakravarthy, VR: Vineeta Rath, PS: Pragya Sharma
 
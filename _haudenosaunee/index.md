---
layout: page
title: The Haudenosaunee Confederacy
permalink: /haudenosaunee/home/
---

<div class="page-content-wrapper">
    <div class="plug">
        <div class="section-head">{{ page.title }}</div>
        <div class="section-description"><em>"The chiefly virtues most prized in Iroquois folklore are those associated with harmony and consensus: imperturbability, patience, good will, selflessness. “The thickness of their skin shall be seven spans—which is to say that they shall be proof against anger, offensive actions and criticism,” the Peacemaker decreed of the League Sachems." - Deganawidah the Great Peacemaker, as quoted by D. K. Richter</em></div>
    </div>

    <div class="topic">
        <div class="article">
        <div class="article-body">
        <img src="{{ baseurl }}/assets/img/sixnations/iroquois-flag-small.png" alt="Haudenosaunee flag" style="float: right; margin-left: 20px; width: 200px" />

        <p>The <em>Haudenosaunee</em> are a confederation of First Nations peoples that had inhabited the rolling hills and rich, well watered lands south of Lake Ontario. Originally numbering five Iroquois-speaking nations (Seneca, Cayuga, Oneida, Onondaga and Mohawk), they were later joined in the 18th century by the Tuscarora nation. The Haudenosaunee was, and still is, a unique confederacy of First Nations that developed before the arrival of the Europeans. Despite their small numbers, they became a very powerful alliance that successfully resisted frequent attempts to defeat them in battle. They learned how to navigate the difficult diplomacy between the French, then Dutch and finally the British colonies. Skillful in warfare, trade and technology, they were sought after as allies by European colonial governments.</p>
    
        <p>During the American Revolution the Haudenosaunee fought alongside the British (with some exceptions). When the British lost the thirteen colonies to the rebels, American soldiers and settlers went about persecuting any who remained loyal to the British, and that included the Six Nations. As a result, most moved into British-controlled Canada and were granted large tracts of land in Upper Canada along the Grand River, the St. Lawrence River and the north-eastern shore of Lake Ontario.</p> 
                        
        <p>This is their story.</p>

        <div class="note">
                    <p><b>Note</b></p>
                    <p>I am not a member of any Iroquois nation so I can only write what I have read and learned. I don't claim to speak for any Iroquois nor do I wish to appropriate to myself any of their beliefs or cultures. What is written in these articles is gleaned from reading authoritative books and articles. Please refer to the many websites owned and maintained by the successor First Nations peoples of the Iroquois. That being said, perhaps the most important person in my late teenage years was a man who as my mentor and tutor was a member of the Blackfoot Nation of Alberta. So, I suppose writing this history is personal.</p>
                </div>

        <h1>Contents</h1>
        {% for item in site.data.haudenosaunee.toc %}
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

---
layout: lay_tag
title: 标签
permalink: /tags/
---

<div class="container">
<div class="row">
  <div class="col-md-12">
    <div class="well" style="height:400px">
    <h4><i class="glyphicon glyphicon-paperclip"></i>分类<i class="glyphicon glyphicon-tag"></i>标签</h4> 
    <div id="screen" class="screen" style="height:400px">
        {% for category in site.categories %}  
        <a href="/tags?type=cat&cname={{ category | first }}" style="color: green; left: 585px; top: 208px; font-size: 15px; z-index: 220; opacity: 0.806138613033569;display:none">
          {{ category | first }}<span class="badge">{{ category | last | size }}</span>
        </a>
        {% endfor %}
        {% for tag in site.tags %} 
        <a href="/tags?type=tag&cname={{ tag | first }}" style="color: green; left: 585px; top: 208px; font-size: 15px; z-index: 220; opacity: 0.806138613033569;">
          {{ tag | first }}<span class="badge">{{ tag | last | size }}</span>
        </a>
        {% endfor %} 
    </div>
    </div>
  </div>
</div>
<div class="row">
  <div class="col-md-12">
     {% for post in site.posts %}
     <div class="art cat_{{ post.categories | first }} tag_{{ post.tags | first }}" style="border-left:5px #AA6708 solid;border-radius:3px;padding:10px;margin-bottom:5px;display:none">
      <a class="post-link" href="{{ post.url | prepend: site.baseurl }}" target="_blank">{{ post.date | date: "%m-%d-%Y" }}-{{ post.title }}</a>
      <span style="float:right"><i class="glyphicon glyphicon-paperclip"></i> {{ post.categories }} <i class="glyphicon glyphicon-tag"></i> {{ post.tags }}</span>
     </div>
     {% endfor %}
  </div>
</div>

</div>

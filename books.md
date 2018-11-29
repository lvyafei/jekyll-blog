---
layout: lay_page
title: 书籍
permalink: /books/
---

<div class="container">
  <div class="row">
    <div class="col-md-1"></div>
    <div class="col-md-11">
      <div class="row">
         <div id="menu">
          <ul>
            {% for site in site.data.custom.books %}
              {% if forloop.first == true %}
           <li data-target="{{ site.id }}" class="selected">{{ site.title }}</li>
              {% endif %}
              {% if forloop.first == false %}
           <li data-target="{{ site.id }}">{{ site.title }}</li>
              {% endif %}
             {% endfor %}
         </ul>
        </div>
    </div>
    <div class="row">
        <div id="content">
         {% for site in site.data.custom.books %}
          {% if forloop.first == true %}
             <div id="{{ site.id }}" class="conts selected">
          {% for cont in site.booklist %}
            <div class="col-md-3">
                <div class="row" style="text-align:center">
                   <a href="{{ cont.douban }}" target="_blank"><image class="imageSize" src="{{ cont.icon }}"></image></a>
                </div>
                <div class="row" style="text-align:center">
                  <span>{{ cont.name }}</span>  
                </div>
            </div>
          {% endfor %}
            </div>
        {% endif %}
        {% if forloop.first == false %}
             <div id="{{ site.id }}" class="conts ">
          {% for cont in site.booklist %}
            <div class="col-md-3">
                <div class="row" style="text-align:center">
                   <a href="{{ cont.douban }}" target="_blank"><image class="imageSize" src="{{ cont.icon }}"></image></a>
                </div>
                <div class="row" style="text-align:center">
                  <span>{{ cont.name }}</span>  
                </div>
            </div>
          {% endfor %}
          </div>
        {% endif %}
        {% endfor %}
      </div>
    </div>
    </div>
  </div>
</div>
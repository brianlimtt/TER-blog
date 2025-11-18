---
layout: default
title: Brian Lim's Blog
---
# <strong>Introduction

<strong>Welcome to my super blog dedicated to the things that I learned throughtout the TER course taken in Grade 11. <br>
<strong>This blog features notes, ideas, comments and other discoveries I make. <br> 

<strong>You can explore a list of the blogs I have written below: <br>

## Table of Contents
Here are my latest posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %-d, %Y" }}
    </li>
  {% endfor %}
</ul>

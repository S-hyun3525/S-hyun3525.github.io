---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

# 안녕 나를 소개하지 이름은 오세민 직업은 트레블러 가사에 욕을 싹다 털어넣어
평화는 질리는 맛이기에 **컴소공 사랑해**

---
### 최근 게시물

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} - <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
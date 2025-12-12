---
layout: default
---

# Halo, Saya Indi9o 👋

Selamat datang di **Jurnal Teknis** saya.

---

## 📝 Daftar Artikel

<ul>
  {% for post in site.posts %}
    <li>
      <span style="color: #666; font-size: 0.8em;">{{ post.date | date: "%Y-%m-%d" }}</span> — 
      <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a>
    </li>
  {% endfor %}
</ul>

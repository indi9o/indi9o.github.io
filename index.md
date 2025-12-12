---
layout: default
---

# Halo, Saya Alan 👋

Selamat datang di **Jurnal Teknis** saya.

Di sini saya menuliskan catatan, pengalaman, dan hal-hal teknis yang saya pelajari sehari-hari sampai solusi atas masalah yang sering ditemui. Catatan ini dibuat untuk dokumentasi pribadi, sekaligus berbagi agar bisa bermanfaat bagi orang lain.

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

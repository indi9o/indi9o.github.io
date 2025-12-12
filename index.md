---
layout: default
---

<div style="width: 100%; margin-bottom: 30px;">
    <img src="/images/banner.jpeg" alt="Header Banner" style="width: 100%; height: auto; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
</div>

# Halo, Saya Alan 👋

Selamat datang di **Jurnal Teknis** saya.

Di sini saya menuliskan catatan, pengalaman, dan hal-hal teknis yang saya pelajari sehari-hari sampai solusi atas masalah yang sering ditemui. Catatan ini dibuat untuk dokumentasi pribadi, sekaligus berbagi agar bisa bermanfaat bagi orang lain.

---

## 🎯 Website ini digunakan untuk:
- **Dokumentasi teknis**: Supaya kalau saya lupa, tinggal buka blog ini lagi.
- **Catatan belajar**: Siapa tahu teman-teman ada yang mengalami masalah sama, jadi bisa terbantu lewat tulisan di sini.

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

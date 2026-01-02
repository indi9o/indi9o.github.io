---
layout: post
title: "Backup Data Pribadi di Laptop Linux Menggunakan RSYNC"
categories:
  - Linux
  - Ubuntu
  - Backup
  - Tutorial
tags:
  - rsync
  - backup data
  - linux
  - hard disk eksternal
  - ubuntu
  - tutorial
description: "Catatan praktis melakukan BACKUP data pribadi di laptop Linux menggunakan RSYNC"
date: 2025-01-02
---

# Halo 👋. Backup Data Pribadi di Laptop Linux Menggunakan RSYNC

BACKUP data pribadi di laptop biasanya baru terpikir ketika ada masalah. Padahal, justru saat tidak ada masalah BACKUP seharusnya dilakukan secara rutin. Selama laptop masih bisa digunakan, file masih bisa dibuka, dan penyimpanan belum penuh BACKUP sering dianggap bukan prioritas.

Saya pun memulainya dengan cara sederhana. Setiap kali menyalin direktori "Documents" ke hard disk eksternal. Tidak terjadwal, tidak ada catatan. Kalau ingat dilakukan, kalau tidak ya lewat begitu saja :). Sampai suatu saat saya sendiri tidak yakin: kapan terakhir backup dilakukan dan apakah isinya masih sama dengan data di laptop.

Seiring waktu, data pribadi menjadi bertambah. Dokumen kerja, arsip lama, catatan, dan berbagai file lain menumpuk di satu folder. Ukuran data semakin besar, proses salin (copy) ke hard disk external semakin lama, dan backup manual mulai terasa tidak efisien.

<div style="width: 100%; margin-bottom: 30px;">
    <img src="/images/infografis_backup_rsync.jpeg" alt="infografis_backup_rsync" style="width: 100%; height: auto; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
</div>

## ❌ Problem
Menyalin direktori atau file secara manual tidak memberi informasi apakah semua file sudah benar-benar tersalin. Jika proses BACKUP berhenti di tengah jalan, kita jarang melakukan cek ulang. Masalah lain muncul ketika setiap kali ada perubahan direktori atau file, seluruh direktori harus disalin (copy) ulang. Prosesnya memakan waktu lama dan membosankan (BACKUP makin jarang dilakukan :).

Untuk mengatasi hal ini, saya mulai menggunakan RSYNC. Alasannya sederhana: RSYNC hanya menyalin file yang berubah. BACKUP berikutnya menjadi jauh lebih cepat.

## ✅ Solution
RSYNC cocok juga untuk BACKUP data pribadi. RSYNC dirancang untuk sinkronisasi, bukan hanya sekedar menyalin (copy). Setiap kali dijalankan, RSYNC membandingkan data sumber dan tujuan, lalu hanya memproses data yang berbeda.

## 🛠️ Implementasi: Backup Data Pribadi dengan RSYNC
Dalam praktik sehari-hari, Direktori yang sering dibackup adalah "Documents". Hard disk eksternal biasanya akan  ter-mount otomatis di "/media". Dengan asumsi ini, perintah RSYNC yang digunakan adalah:
```bash 
rsync -avh --progress \
/home/user/Documents/ \
/media/user/EXT_DISK/BackupDocuments/
```
Perintah ini adalah salin (copy) isi direktori "Documents" ke hard disk eksternal direktori "BackupDocuments". Opsi -a menjaga struktur direktori dan timestamp, --progress membantu melihat proses BACKUP berjalan.

### 🔍 Verifikasi
Ketika BACKUP selesai dijalankan, perlu dilakukan verfikasi untuk memastikan hasil BACKUP sesuai dengan sumber, saya menggunakan opsi --dry-run.
```bash
rsync -avh --progress --dry-run \
/home/user/Documents/ \
/media/user/EXT_DISK/BackupDocuments/
```
Dengan opsi ini, RSYNC hanya membandingkan sumber dan tujuan tanpa menyalin (copy) data. Jika tidak ada output, berarti data sumber dan tujuan sudah sama. Untuk backup data pribadi, metode ini sudah cukup efektif.

## 📌 Lesson Learned: BACKUP Itu Soal Kebiasaan
Dari pengalaman menggunakan RSYNC untuk BACKUP data pribadi, saya menyimpulkan bahwa BACKUP bukan soal menggunakan tool yang paling canggih, tetapi ini soal kebiasaan untuk mengamankan data. BACKUP yang sederhana tetapi rutin jauh lebih efektif/bermanfaat. BACKUP yang aman adalah BACKUP yang dilakukan secara berkala dan hasilnya perlu diverifikasi.

## 🔚 Penutub
BACKUP data pribadi di laptop Linux dengan tool RSYNC, membuat proses BACKUP lebih sederhana, efisien, dan bisa diulang kapan saja. RSYNC saat ini sudah cukup untuk kebutuhan sehari-hari. 





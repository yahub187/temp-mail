# Avix Temp Mail

**Temp Mail** adalah sistem email sementara (_temporary email_) personal dan open-source milik **yahub187**. Proyek ini dibuat untuk menerima email verifikasi akun (misalnya kode OTP dan tautan konfirmasi) tanpa harus memakai alamat email utama.

🌐 **Situs proyek:** https://yahub187.github.io/temp-mail/

## Cara kerja

Sistem ini dirancang dengan arsitektur berikut:

- **Postfix** — menerima email masuk (SMTP) untuk domain `avixmail.is-a.dev`.
- **Dovecot** — menyimpan dan melayani kotak masuk (IMAP) untuk setiap mailbox sementara.
- **FastAPI** — API dan antarmuka web untuk membuat mailbox, melihat pesan masuk, dan mengelola kartu mailbox.
- **ImprovMX** — menangani penerimaan email (MX/TXT) pada domain `avixmail.is-a.dev`.

## Kartu mailbox

Setiap mailbox dibuat secara acak dan direpresentasikan sebagai kartu dengan format:

```
email|password|other|link
```

- **email** — alamat email sementara, contoh: `namaacak@avixmail.is-a.dev`
- **password** — kata sandi untuk mengakses mailbox
- **other** — catatan tambahan (misalnya layanan tempat email dipakai)
- **link** — tautan untuk membuka kotak masuk mailbox tersebut

## Penggunaan

1. Buat mailbox baru — sistem akan menghasilkan alamat acak di `avixmail.is-a.dev` beserta kata sandinya.
2. Gunakan alamat tersebut saat mendaftar atau meminta verifikasi pada suatu layanan.
3. Buka kotak masuk lewat tautan pada kartu mailbox dan baca email verifikasi yang masuk.
4. Mailbox bersifat sementara: jangan gunakan untuk hal penting atau jangka panjang.

## Status

🚧 **Dalam pengembangan (_in development_)** — arsitektur dan antarmuka masih dikerjakan. Email masuk saat ini diterima melalui ImprovMX pada domain `avixmail.is-a.dev`.

## Domain

- **Situs proyek (GitHub Pages):** https://yahub187.github.io/temp-mail/
- **Domain email:** `avixmail.is-a.dev` — digunakan untuk penerimaan email (MX/TXT via ImprovMX), bukan sebagai situs web.

## Pemilik

Proyek ini dikelola oleh **yahub187** sebagai proyek perangkat lunak personal dan non-komersial.

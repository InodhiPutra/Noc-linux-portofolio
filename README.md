# Nama Proyek (singkat dan jelas)

> Satu kalimat ringkasan: apa yang dibangun dan masalah apa yang diselesaikan.
> Contoh: Linux gateway dengan OSPF (FRRouting) yang terhubung ke router Cisco, lengkap dengan uji failover.

![Status](https://img.shields.io/badge/status-selesai-green)
![Lab](https://img.shields.io/badge/lab-GNS3-blue)

## 1. Tujuan

- Apa yang ingin dicapai dari proyek ini?
- Skill apa yang ditunjukkan? (contoh: routing dinamis, monitoring SNMP, hardening)

## 2. Topologi dan Arsitektur

![Diagram topologi](docs/topologi.png)

| Perangkat | Peran | OS / Image | IP Address |
|---|---|---|---|
| R1 | Router Cisco | IOSv | 10.0.0.1/30 |
| linux-gw | Gateway Linux | Ubuntu Server 24.04 | 10.0.0.2/30 |
| ... | ... | ... | ... |

Tabel pengalamatan dan VLAN (kalau ada):

| VLAN | Nama | Subnet |
|---|---|---|
| 10 | Server | 192.168.10.0/24 |

## 3. Kebutuhan (Prerequisites)

- Platform lab: (GNS3 / CML / EVE-NG, versi berapa)
- Spesifikasi minimum: (RAM, CPU, disk)
- Software dan paket: (FRRouting, Zabbix, Netmiko, dll. beserta versinya)

## 4. Langkah Implementasi

### 4.1 Persiapan
Jelaskan langkah awal. Sertakan perintah yang dijalankan:

```bash
sudo apt update && sudo apt install -y frr
```

### 4.2 Konfigurasi
Jelaskan tiap bagian konfigurasi dan alasannya, bukan hanya perintahnya.

```
! contoh konfigurasi Cisco
router ospf 1
 network 10.0.0.0 0.0.0.3 area 0
```

### 4.3 Struktur repo

```
.
├── README.md
├── configs/        # konfigurasi perangkat (kredensial sudah disensor)
├── scripts/        # skrip bash/python/ansible
├── docs/           # diagram dan screenshot
└── results/        # output pengujian
```

## 5. Pengujian dan Hasil

| Skenario uji | Hasil yang diharapkan | Hasil aktual | Status |
|---|---|---|---|
| Ping antar-VLAN | Berhasil | Berhasil | OK |
| Putus link utama | Failover < 10 detik | 6 detik | OK |

Sertakan screenshot atau output perintah (`show ip ospf neighbor`, `ping`, `traceroute`, dll.).

## 6. Troubleshooting

Masalah yang ditemui saat mengerjakan, penyebab, dan solusinya. Bagian ini menunjukkan cara Anda berpikir.

| Masalah | Penyebab | Solusi |
|---|---|---|
| OSPF neighbor stuck di EXSTART | MTU tidak cocok | Samakan MTU di kedua sisi |

## 7. Pelajaran yang Didapat

- Apa yang berjalan baik?
- Apa yang akan dilakukan berbeda?
- Pengembangan berikutnya.

## 8. Catatan Keamanan

- Seluruh kredensial, IP publik, dan data asli sudah disensor atau diganti data lab.
- Proyek ini dibuat di lingkungan lab, bukan di sistem produksi.

## 9. Referensi

- Dokumentasi resmi yang dipakai (tautan)

## Penulis

**Nama Anda**
BNSP Jaringan | MTCNA | (tambahkan sertifikat lain)
[LinkedIn](#) | [Medium](#) | [GitHub](#)
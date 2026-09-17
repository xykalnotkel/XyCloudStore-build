# XyCloudStore Build & Releases

Repositori publik ini hanya memuat workflow build manual dan artefak rilis XyCloudStore. Source utama, backend, dashboard admin, serta konfigurasi operasi tetap berada di repositori privat.

## Keamanan

- Workflow hanya berjalan melalui **workflow_dispatch**; tidak ada build otomatis pada push/PR.
- Source diambil dengan deploy key **read-only** dan credential tidak dipersist ke Git.
- Secret penandatangan APK tersimpan sebagai GitHub Actions secrets dan tidak pernah dicetak atau dimasukkan ke artefak.
- APK selalu disertai corresponding-source bundle untuk komponen GPL yang didistribusikan.
- Rilis resmi hanya berasal dari workflow pada branch/tag yang dikelola pemilik.

Unduh APK dan Agen Windows melalui tab **Releases** atau **Actions → Artifacts**.

# XyCloudStore Build & Releases

Repositori publik ini hanya memuat workflow build manual dan artefak rilis XyCloudStore. Source utama, backend, dashboard admin, serta konfigurasi operasi tetap berada di repositori privat.

## Keamanan

- Workflow hanya berjalan melalui **workflow_dispatch**; tidak ada build otomatis pada push/PR.
- Checkout bersifat sparse: job APK hanya mengambil `app`, `native`, dan tool build; job Agen hanya mengambil `agent-gui`. Backend/dashboard tidak pernah masuk workspace runner publik.
- Source diambil dengan deploy key **read-only**; berkas key langsung dihapus sebelum toolchain atau dependency pihak ketiga berjalan.
- Semua Actions pihak ketiga dipin ke commit SHA. Token `contents: write` hanya tersedia pada job publikasi terpisah.
- Secret penandatangan APK tersimpan sebagai GitHub Actions secrets, tidak pernah dicetak/dimasukkan ke artefak, dan build gagal tertutup bila signing tidak lengkap.
- APK selalu disertai corresponding-source bundle GPL terverifikasi yang menolak direktori backend, dashboard, agent, runbook, dan workflow privat.
- Rilis resmi hanya berasal dari workflow pada branch/tag yang dikelola pemilik.

Unduh APK dan Agen Windows melalui tab **Releases** atau **Actions → Artifacts**.

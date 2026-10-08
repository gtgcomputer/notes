# notes

Kumpulan script utilitas GTG COMPUTER.

## Blokir Internet AutoCAD (folder `autocad/`)

Script `.bat` sekali-jalan untuk memutus total akses internet AutoCAD
(tanpa install ulang Windows). Pilih sesuai versi yang terinstall.

| File | Untuk |
|---|---|
| `autocad/blokir-autocad-2018.bat` | AutoCAD 2018 |
| `autocad/blokir-autocad-2025.bat` | AutoCAD 2025 |

### Cara pakai

Copy-paste salah satu perintah ini di **PowerShell** (klik kanan > Run as Administrator
tidak perlu — script minta sendiri otomatis):

**AutoCAD 2018:**
```powershell
irm https://raw.githubusercontent.com/gtgcomputer/notes/main/autocad/blokir-autocad-2018.bat -OutFile $env:TEMP\s.bat; saps $env:TEMP\s.bat -Verb RunAs
```

**AutoCAD 2025:**
```powershell
irm https://raw.githubusercontent.com/gtgcomputer/notes/main/autocad/blokir-autocad-2025.bat -OutFile $env:TEMP\s.bat; saps $env:TEMP\s.bat -Verb RunAs
```

### Yang dilakukan script

1. **Firewall** — blokir koneksi keluar (outbound) `acad.exe` dan kawan-kawan
2. **Service** — disable service Autodesk (lisensi, desktop app, dsb)
3. **Hosts** — arahkan 9 domain server Autodesk ke `127.0.0.1`

### Catatan

- Aman dijalankan berulang-ulang (idempotent).
- Butuh hak Administrator (otomatis diminta saat dijalankan).
- Setelah blokir, **restart PC** agar efek penuh.
- Dibuat oleh GTG COMPUTER - WA 085738127969.

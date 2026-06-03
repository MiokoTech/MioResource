# MyResource — MioNova Ped Model Repository

Repo private untuk ped model files yang dipakai sistem generate install MioNova.

## Struktur

```
peds/
├── normal/
│   ├── manifest.json          ← daftar semua normal peds
│   └── {ped_id}/
│       ├── preview_1.png      ← foto pose 1 (untuk Window 3)
│       ├── preview_2.png      ← foto pose 2
│       ├── preview_3.png      ← foto pose 3
│       ├── {ped_id}.ytd       ← texture file
│       └── {ped_id}.yft       ← model file
│
├── boss/
│   ├── manifest.json
│   └── {ped_id}/
│       ├── preview_1.png
│       ├── preview_2.png
│       ├── preview_3.png
│       ├── {ped_id}.ytd
│       └── {ped_id}.yft
│
└── group/
    ├── manifest.json
    └── {group_id}/
        ├── preview_1.png      ← preview tim (bukan per member)
        ├── preview_2.png
        ├── preview_3.png
        └── {member_id}/
            ├── {member_id}.ytd
            └── {member_id}.yft
```

## Manifest Format

### normal/manifest.json & boss/manifest.json
```json
{
  "type": "normal",
  "peds": [
    {
      "id": "levi",
      "name": "Levi Ackerman",
      "previews": ["preview_1.png", "preview_2.png", "preview_3.png"],
      "files": ["levi.ytd", "levi.yft"]
    }
  ]
}
```

### group/manifest.json
```json
{
  "type": "group",
  "groups": [
    {
      "id": "avengers",
      "name": "Avengers",
      "previews": ["preview_1.png", "preview_2.png", "preview_3.png"],
      "members": [
        { "id": "thanos",   "name": "Thanos",   "files": ["thanos.ytd",   "thanos.yft"]   },
        { "id": "thor",     "name": "Thor",      "files": ["thor.ytd",     "thor.yft"]     },
        { "id": "iron_man", "name": "Iron Man",  "files": ["iron_man.ytd", "iron_man.yft"] }
      ]
    }
  ]
}
```

## Naming Rules

- `id` = nama folder, huruf kecil + underscore, tanpa spasi
- `files` = nama file PERSIS seperti yang ada di folder
- Preview: 3 gambar, salah satu dipilih random saat install
- Model files masuk ke `addonpeds.rpf` (enemy) atau `streamedpeds_chr.rpf` (player)

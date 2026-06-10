# conocimiento-backup

Repositorio de backups automáticos del stack **BookStack + Nginx Proxy Manager**.

## Estructura

```
CONOCIMIENTO/
├── BOOK/                            # Stack Docker (no versionado)
├── BACKUPS/
│   └── YYYYMMDD-HHMMSS/
│       ├── bookstack_files.tar.gz   # Ficheros BookStack (/config)
│       ├── npm_files.tar.gz         # Datos + certs NPM
│       ├── bookstackapp.sql.gz      # Dump MariaDB
│       ├── compose.yaml             # Docker Compose
│       ├── .env                     # Variables de entorno
│       └── info.txt                 # Metadatos del backup
└── logs/
    └── operaciones.log              # Log unificado
```

## Scripts

| Script | Descripción |
|---|---|
| `BOOK/backup.sh` | Genera backup y lo sube a este repo |
| `BOOK/restore.sh` | Restaura desde el backup más reciente (o uno específico) |

## Restaurar un backup específico

```bash
./BOOK/restore.sh 20250610-142500
```

Sin argumento → usa siempre el más reciente.
# CONOCIMIENTO-BACKUP

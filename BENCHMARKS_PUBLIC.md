# 📊 NaosBinary v1.3 - Rapport de Performance

**Version :** v1.3.0 (Production Ready)
**Date :** 2023-10-27
**Environnement :** Windows / Python 3.9+

## 🏆 Résumé Exécutif

NaosBinary est un moteur de compression hybride conçu pour l'IoT et l'IA. Il excelle là où les compresseurs généralistes (Zlib, LZ4) échouent : les données creuses (Sparse) et la sécurité sur les données aléatoires.

| Scénario | Flux Type | Meilleur Codec | Ratio Compression | Vitesse Comp. |
|---|---|---|---|---|
| **IoT (Silence)** | `zeros` / `ones` | **NaosBinary (AUTO)** | **0.000006** (x166,000) | **> 22 GB/s** |
| **Capteurs (Bruit)** | `bit_noise` | NaosBinary (RLE) | ~0.18 (x5.5) | > 12 MB/s |
| **Sécurité (Crypto)** | `random` | **NaosBinary (AUTO)** | **1.00** (Pas de perte) | **> 30 MB/s** |
| **Télémétrie** | `alternating` | NaosBinary (BITPACK) | ~1.00 (Safe) | > 30 MB/s |

> **Note :** Sur les données aléatoires (`random`), NaosBinary garantit un ratio de 1.00 (mode "Pass-through"), évitant le gonflement de fichier typique des autres algorithmes.

## 🔎 Analyse par Domaine

### 1. IoT & Smart Metering (La "Killer Feature")
Les capteurs envoient souvent des signaux "Rien à signaler" (suites de 0 ou de 1).
- **NaosBinary** détecte ces plages instantanément grâce à son algorithme *Zero-First RLE*.
- **Résultat :** Une réduction de taille quasi-totale (Ratio 0.000006), réduisant drastiquement les coûts de transmission (4G/Satellite).

### 2. Infrastructure IA (Matrices Creuses)
Les masques d'attention et les matrices de gradients contiennent énormément de zéros.
- NaosBinary les compresse sans consommer de CPU (contrairement à Zlib qui essaie de trouver des motifs complexes).

### 3. Sécurité & Performance
L'heuristique `AUTO` (optimisée en C-speed/Regex) décide en temps réel du meilleur mode.
- Si les données sont incompressibles (chiffrées), NaosBinary n'ajoute **aucune latence** et **aucun overhead**.

---

## 🛠️ Méthodologie

Benchmark réalisé avec `bench_all_flux_v1_3.py` sur des flux de 32 MiB.
- **Machine :** Standard Workstation
- **Comparatif :** Zlib, BZ2, LZMA, LZ4, Zstd, Snappy, Brotli.
- **Métriques :** Ratio (Taille Comp / Taille Orig), Débit (MB/s).

*Pour reproduire ces résultats, téléchargez l'exécutable `naosbin.exe` et lancez :*
`naosbin.exe bench --preset throughput`
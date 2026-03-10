# 📊 NaosBinary v2.1 - Performance & Routing Benchmarks

Contrairement aux compresseurs statiques traditionnels (Zlib, LZ4, Zstd) qui s'exécutent de manière aveugle au détriment du CPU, **NaosBinary Native-x** intègre un routage intelligent adaptatif.

Le moteur analyse l'entropie à la volée et bascule entre la **Réduction Algorithmique** et le **Contournement Matériel (Bypass)**. Toutes les opérations garantissent une intégrité absolue, vérifiée par empreinte cryptographique native.

## 🩺 Crash-Test Industriel : MedTech & Imagerie (Mars 2026)

L'évaluation de la version **2.1 (Native-x)** a été réalisée sur un volume de données d'imagerie médicale (IRM) réelles, exigeant une politique de tolérance zéro sur la corruption de données.

| Paramètre | Résultat Validé |
| :--- | :--- |
| **Volume Traité** | 4.13 Go |
| **Nombre de fichiers** | 15 783 fichiers séquentiels |
| **Temps Total** | 314.38 secondes |
| **Intégrité Cryptographique** | ✅ 100% SHA-256 MATCH (Lossless) |

### Comportement du Cerveau Hybride en conditions réelles :

Durant ce traitement, le moteur de **104 Ko** a pris plus de **15 700 décisions** de routage à la volée, sans aucune fuite de mémoire :

* **🟩 OPTIMISATION DYNAMIQUE :** Déclenchée sur la majorité des coupes anatomiques. Le moteur a réduit le volume de manière chirurgicale, avec des pics de réduction atteignant un **ratio de 0.18** (plus de 80% d'écrasement volumétrique).
* **🟦 ROUTAGE PASSIF :** Déclenché instantanément et silencieusement sur les fichiers locaux présentant un bruit statistique trop élevé. Le moteur a appliqué un ratio de 1.0000, sécurisant le transfert sans consommer de cycles CPU inutiles.

> **Note de l'ingénierie :** La vitesse brute n'est plus la métrique principale de Native-x. La v2.1 priorise le déterminisme, la sécurité absolue du flux (0 bit perdu), et l'efficience énergétique sur architecture Edge. L'intégration du SHA-256 natif garantit une souveraineté totale de la donnée restaurée.

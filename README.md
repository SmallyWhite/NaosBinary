# 🚀 NaosBinary v1.3 - Hybrid High-Speed Compression

**NaosBinary** est un moteur de compression binaire propriétaire ultra-rapide optimisé pour les données IoT, la télémétrie LPWAN et les matrices creuses pour l'IA.

Il utilise une approche systémique unique pour atteindre des débits dépassant les **22 GB/s** sur des flux spécifiques, tout en garantissant une sécurité totale sur les données aléatoires.

## ✨ Points Forts (v1.3)
- **Vitesse Extrême :** > 22 GB/s sur flux structurés (IoT/Silence).
- **Zéro Gonflement :** Ratio de **1.00 garanti** sur données aléatoires ou chiffrées (Mode Pass-through).
- **Efficacité IoT :** Ratio de compression jusqu'à **0.000006** (x166,000) sur les suites de bits répétitives.
- **Léger :** Conçu pour une latence prédictible et une faible consommation CPU.

## 📊 Performance en un clin d'œil
| Flux Type | Codec | Ratio | Vitesse |
|---|---|---|---|
| IoT (Silence) | AUTO | **0.000006** | **22 GB/s** |
| Crypto (Random) | AUTO | **1.00** | 30 MB/s |

*Détails complets dans le fichier [BENCHMARKS.md](./BENCHMARKS.md).*

## 🚀 Tester la Performance
Le code source est propriétaire, mais vous pouvez tester la puissance du moteur :
1. Téléchargez l'exécutable dans `/bin`.
2. Lancez `demo/demo_script.bat` pour voir les résultats sur votre machine.

## 📩 Contact
**Stephen Hengel** Email : mr.hengel.stephen@gmail.com
---

## ⚖️ Licence & Usage
L'exécutable fourni dans ce dépôt est destiné exclusivement à des fins d'**évaluation technique et de démonstration**. 
- Toute utilisation commerciale, redistribution ou ingénierie inverse est strictement interdite sans une licence explicite.
- Pour obtenir une licence commerciale (accès aux bibliothèques d'intégration, support technique, code source), veuillez me contacter par email.

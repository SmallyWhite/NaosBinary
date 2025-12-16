# NaosBinary

NaosBinary est un codec de compression binaire propriétaire, conçu pour des
payloads IoT / LPWAN (bitmasks, flags, champs binaires structurés).

Il vise une classe précise de données binaires pour lesquelles les codecs
généralistes (zlib, zstd, brotli, etc.) sont inefficaces, tout en restant neutre
sur les données à forte entropie.

NaosBinary n’a pas vocation à remplacer les codecs généralistes.
Il agit comme une couche de compression spécialisée, là où cela a du sens.

---

## Principes de conception

NaosBinary repose sur trois principes simples :

- Compresser très fortement lorsque la structure binaire s’y prête
- Ne jamais dégrader significativement les données aléatoires
- Garantir une latence faible et prédictible sur de petits payloads

Le comportement est déterministe, sans modèle statistique,
sans apprentissage, et sans effet de bord.

---

## Architecture (v1.3)

NaosBinary v1.3 s’appuie sur deux mécanismes simples :

- **RLE-1**  
  Un Run-Length Encoding optimisé pour les longues séquences de bits à `1`.

- **BitPack**  
  Un empaquetage binaire compact utilisé lorsque le RLE n’apporte aucun gain.

Un sélecteur automatique choisit le mode le plus adapté à l’encodage.
Lorsque la compression n’est pas bénéfique, un bypass propre est effectué
(ratio proche de 1.00).

---

## Propriétés clés

- Comportement déterministe
- Pas d’explosion de taille sur données aléatoires
- Latence d’encodage / décodage très faible
- Adapté aux environnements embarqués, edge et gateway
- Aucune modification matérielle requise

---

## Résultats de benchmarks

Les benchmarks complets sont disponibles dans le dossier `benchmarks/`.

Résultats représentatifs :

- **Données très structurées (`all_ones`, 100 000 bits)**  
  Entrée : 12 500 octets  
  Sortie : 5 octets  
  Ratio ≈ 0,0004 (≈ ×3000)

- **Données aléatoires / blocky**  
  Ratio ≈ 1,0003  
  Sélection automatique du BitPack (bypass propre)

- **Latence (blocs de 2048 bits)**  
  Encodage ≈ 0,19 ms  
  Décodage ≈ 0,18 ms

Tous les tests de roundtrip sont validés sans corruption de données.

---

## Contexte d’intégration

[Application / Capteur]
|
v
[NaosBinary]
|
v
[Stack LoRaWAN / IP]

yaml
Copier le code

Le décodage est effectué de manière symétrique côté réception.

---

## Disponibilité du code source

Le code source de NaosBinary n’est pas public.

Ce dépôt fournit une documentation technique et des benchmarks
dans le cadre d’évaluations et de discussions de POC.

Les binaires ou bibliothèques sont fournis sous NDA.

---

## Contact

Stephen Hengel  
Créateur de NaosBinary  
Email : mr.hengel.stephen@gmail.com

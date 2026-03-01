# TP2 - Traitement par Lot et Streaming avec Apache Spark

## 📚 Informations

| | |
|---|---|
| **Module** | Big Data |
| **Classe** | Master 1 SRT-GLSI |
| **Année** | 2025-2026 |
| **Encadreur** | M. Ba |
| **École** | École Supérieure Polytechnique de Dakar |

## 👥 Groupe 2

- Moussa Sow
- Djibril Kane Diallo
- Hadia Rougui Sow
- Mouhamed El Bachir Diop

## 🎯 Objectifs

Utilisation de Spark pour réaliser des traitements par lot et des traitements en streaming.

## 🛠️ Outils et Versions

| Outil | Version |
|-------|---------|
| Apache Hadoop | 2.7.2 |
| Apache Spark | 2.2.1 |
| Docker | 17.09+ |
| Java | 1.8 |
| Maven | 3.x |

## 📁 Structure du Projet
```
TP2-Apache-Spark/
├── spark-batch/          # WordCount en Java (Batch)
│   ├── src/
│   └── pom.xml
├── spark-streaming/      # Streaming en Java
│   ├── src/
│   └── pom.xml
├── rapport/              # Rapport LaTeX
└── captures/             # Captures d'écran
```

## 🚀 Parties Réalisées

### Partie 1 - Test avec Spark Shell
- Création du cluster Docker (1 master + 2 slaves)
- Chargement de fichiers dans HDFS
- WordCount en Scala via spark-shell

### Partie 2 - Spark Batch en Java
- Développement d'un WordCount en Java avec Maven
- Test local puis soumission sur cluster via `spark-submit`

### Partie 3 - Spark Streaming
- Traitement de flux en temps réel via sockets TCP
- Comptage de mots en temps réel par micro-batch d'1 seconde

## ▶️ Lancer le Batch
```bash
spark-submit --class tn.insat.tp21.WordCountTask \
  --master local \
  wordcount-1.jar input/purchases.txt output
```

## ▶️ Lancer le Streaming
```bash
# Terminal 1 : créer le flux
nc -lk 9999

# Terminal 2 : lancer l'application
spark-submit --class tn.insat.tp22.Stream \
  --master local \
  stream-1.jar
```

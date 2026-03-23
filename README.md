# 🔗 Python & MySQL

> Projet réalisé en 2024 à **Supinfo Paris**

## 📋 Description

Projet de connexion entre Python et une base de données MySQL. L'objectif était d'automatiser des extractions de données et d'afficher les résultats de manière structurée via des scripts Python.

## 🎯 Objectifs

- Connecter un script Python à une base de données MySQL
- Exécuter des requêtes SQL directement depuis Python
- Récupérer et afficher les résultats sous forme de tableaux
- Automatiser des extractions de données simples

## 🛠️ Technologies utilisées

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)

## 📂 Structure du projet

```
projet-python-mysql/
├── config/
│   └── connexion.py         # Paramètres de connexion à la BDD
├── scripts/
│   ├── extraction.py        # Extraction et affichage des données
│   └── automatisation.py   # Scripts d'automatisation
└── README.md
```

## 💡 Exemple de code

```python
import mysql.connector

# Connexion à la base de données
connexion = mysql.connector.connect(
    host="localhost",
    user="root",
    password="votre_mot_de_passe",
    database="nom_base"
)

curseur = connexion.cursor()

# Exécution d'une requête
curseur.execute("SELECT nom, prenom, salaire FROM employes ORDER BY salaire DESC")

# Récupération et affichage des résultats
resultats = curseur.fetchall()
print(f"{'Nom':<15} {'Prénom':<15} {'Salaire':>10}")
print("-" * 42)
for ligne in resultats:
    print(f"{ligne[0]:<15} {ligne[1]:<15} {ligne[2]:>10.2f} €")

curseur.close()
connexion.close()
```

## 🔍 Ce que j'ai appris

- Utilisation de la bibliothèque `mysql-connector-python`
- Gestion de la connexion et des curseurs
- Récupération des résultats avec `fetchall()` et `fetchone()`
- Affichage formaté des données en tableau dans le terminal
- Automatisation d'extractions récurrentes

## 🚀 Installation

```bash
pip install mysql-connector-python
python scripts/extraction.py
```

---

*Projet académique — Supinfo Paris 2024*

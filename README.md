# ACNAAFarmstat — TP INF232 EC2
## Application de Collecte & Analyse de Données d'Élevage
**Langage :** Python / Django | **Secteur :** Élevage

---

## 🚀 Déploiement sur Render.com (GRATUIT)

### Étape 1 — Préparer GitHub
1. Créer un compte sur [github.com](https://github.com)
2. Créer un nouveau dépôt (ex: `agristat-pro`)
3. Upload tous les fichiers de ce projet

### Étape 2 — Déployer sur Render
1. Aller sur [render.com](https://render.com) → créer un compte gratuit
2. Cliquer **"New +"** → **"Web Service"**
3. Connecter votre dépôt GitHub
4. Remplir les champs :
   - **Build Command :** `./build.sh`
   - **Start Command :** `gunicorn agridata.wsgi`
   - **Environment :** Python 3
5. Cliquer **"Create Web Service"**
6. Attendre 2-3 minutes → votre lien est prêt !

---

## 💻 Lancer en local (Ubuntu)

```bash
# Installer les dépendances
pip3 install -r requirements.txt

# Migrations
python3 manage.py migrate

# Données de démonstration
python3 seed_data.py

# Créer un super-utilisateur (admin)
python3 manage.py createsuperuser

# Lancer
python3 manage.py runserver
```
→ Ouvrir : http://127.0.0.1:8000

---

## 📋 Fonctionnalités

- ✅ Tableau de bord avec 4 graphiques dynamiques
- ✅ Collecte de données : 20+ variables par fiche
- ✅ Gestion CRUD complète des fiches
- ✅ Filtres multi-critères
- ✅ Analyse descriptive : moyenne, médiane, écart-type, min, max, étendue
- ✅ Tableau croisé Espèce × État de santé
- ✅ Nuage de points (corrélation poids ↔ production)
- ✅ Export CSV compatible Excel
- ✅ Interface admin Django

---

## 👨‍💻 Structure du projet

```
agridata/
├── agridata/          # Configuration Django
├── collecte/          # Application principale
│   ├── models.py      # Modèle FicheElevage
│   ├── views.py       # Logique métier + analyses
│   ├── forms.py       # Formulaires
│   └── urls.py        # Routes
├── templates/         # Interface HTML
├── seed_data.py       # Données de démo
├── requirements.txt
├── build.sh           # Script déploiement
└── Procfile
```

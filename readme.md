# 📧 scraper-4-email

**scraper-4-email** est un outil Python permettant d’extraire automatiquement des adresses e-mails (même obfusquées) à partir des sites web listés dans un fichier Excel. Il parcourt les sitemaps, récupère les pages pertinentes et analyse leur contenu textuel pour détecter les adresses e-mail.

---

## 🚀 Fonctionnalités

- 🔍 Récupération automatique des URLs via les fichiers sitemap XML (`/page-sitemap.xml`)
- 🧠 Détection d'e-mails normaux et obfusqués (`[at]`, `(dot)`, `{at}`, etc.)
- 📄 Lecture des sites à scanner depuis un fichier Excel `.xlsx`
- 🧪 Normalisation automatique des e-mails détectés
- 📝 Export final dans un fichier CSV clair et structuré
- 🖥️ Utilisation en **ligne de commande** ou en **script Python**

---

## 📦 Installation

### ▶️ Depuis le code source

```bash
git clone https://github.com/ton-utilisateur/scraper-4-email.git
cd scraper-4-email
pip install .

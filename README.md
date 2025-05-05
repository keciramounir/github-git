
# 🌱 Tutoriel Complet : Git & GitHub (Débutant à Avancé)

---

## 📘 Qu’est-ce que Git ?

> **Git** est un système de **gestion de versions distribué**.
> Il permet de suivre toutes les modifications apportées à un projet (code, documents, etc.), de collaborer à plusieurs sans conflits, et de revenir à une version antérieure du projet à tout moment.

🎯 **Avantages :**

* Sauvegarde de l’historique des fichiers
* Travail collaboratif sans écrasement
* Expérimenter sans casser le projet

---

## ☁️ Qu’est-ce que GitHub ?

> **GitHub** est une plateforme **en ligne** qui héberge des projets Git et facilite la **collaboration**.

🛠️ Tu peux :

* Stocker ton code sur Internet
* Travailler à plusieurs (pull requests)
* Suivre les bugs, les issues
* Héberger des projets open-source

---

## 🏗️ Structure d’un projet Git

| Élément                   | Description                                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------------------- |
| **Repository** (ou dépôt) | Projet contenant tous les fichiers suivis                                                         |
| **Commit**                | Un "instantané" de ton code avec un message                                                       |
| **Branch**                | Une version parallèle du projet, utilisée pour tester, corriger ou développer des fonctionnalités |
| **Remote**                | Une version en ligne du dépôt (ex: sur GitHub)                                                    |
| **Merge**                 | Fusion de deux branches                                                                           |

---

## 🌿 Qu’est-ce qu’une branche (branch) ?

> Une **branche** est une ligne de développement parallèle.
> Tu peux travailler sur une nouvelle fonctionnalité sans impacter le code principal.

* La branche principale s'appelle souvent **`main`** ou **`master`**.
* Tu peux créer une branche pour chaque nouvelle tâche : `feature-login`, `bugfix-css`, etc.

👨‍💻 Exemple :

* `main` : version stable
* `dev` : version de développement
* `feature-x` : nouvelle fonctionnalité en cours

---

# 🛠️ Tutoriel étape par étape avec toutes les commandes

---

## 1. 🔧 Configuration initiale (une seule fois)

```bash
git config --global user.name "Ton Nom"
git config --global user.email "email@exemple.com"
```

✅ Enregistre ton nom et ton email dans Git (important pour chaque commit).

---

## 2. 📁 Créer un dépôt local

```bash
mkdir mon-projet
cd mon-projet
git init
```

* `mkdir` : crée un dossier
* `git init` : initialise un dépôt Git vide

---

## 3. 🔍 Suivre et valider les fichiers

```bash
git status       # Affiche les fichiers suivis et non suivis
git add fichier.html    # Prépare un fichier pour le commit
git add .        # Prépare tous les fichiers
git commit -m "Premier commit"
```

📌 Un **commit** est une sauvegarde avec un message.

---

## 4. 🌿 Travailler avec des branches

```bash
git branch                    # Liste les branches existantes
git branch dev                # Crée une branche 'dev'
git switch dev                # Change de branche
```

✔️ Modifie ton code, fais des commits, puis reviens à la branche principale :

```bash
git switch main
git merge dev   # Fusionne la branche 'dev' dans 'main'
```

---

## 5. ☁️ Lier à GitHub

1. Va sur [github.com](https://github.com)
2. Crée un nouveau repository (sans README)
3. Dans le terminal :

```bash
git remote add origin https://github.com/ton-user/mon-projet.git
```

ou en SSH :

```bash
git remote add origin git@github.com:ton-user/mon-projet.git
```

---

## 6. 📤 Envoyer ton code en ligne

```bash
git push -u origin main
```

* `-u` : lie ta branche locale à celle sur GitHub
* `origin` : nom du dépôt distant
* `main` : nom de la branche

---

## 7. 📥 Récupérer les mises à jour de GitHub

```bash
git pull
```

* Récupère les modifications distantes et les fusionne

---

## 8. 🧹 Nettoyage et suppression

```bash
git rm fichier.txt        # Supprime un fichier suivi
git branch -d nom-branche # Supprime une branche locale
```

---

## 9. 🧠 Historique & comparaison

```bash
git log           # Voir tous les commits
git log --oneline # Version simplifiée
git diff          # Voir les changements non commités
```

---

## 🔄 Annuler / Restaurer

```bash
git restore fichier.txt         # Annule les changements sur un fichier
git reset HEAD fichier.txt      # Enlève un fichier de la zone de staging
git reset --hard HEAD           # Réinitialise tout au dernier commit
```

---

## 🧪 Git Alias (optionnel)

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
```

✅ Tu peux taper `git st` au lieu de `git status`.

---

# 🧾 Résumé des commandes les plus utilisées

| Commande                    | Description                    |
| --------------------------- | ------------------------------ |
| `git init`                  | Initialise un dépôt Git        |
| `git status`                | Affiche l’état actuel          |
| `git add .`                 | Ajoute tous les fichiers       |
| `git commit -m "message"`   | Crée un commit                 |
| `git branch`                | Liste les branches             |
| `git branch nom`            | Crée une branche               |
| `git switch nom`            | Change de branche              |
| `git merge nom`             | Fusionne une branche           |
| `git remote add origin ...` | Lie à GitHub                   |
| `git push` / `git pull`     | Envoie / récupère du code      |
| `git log` / `git diff`      | Historique / différences       |
| `git rm` / `git restore`    | Supprime / restaure un fichier |







---------------------------------------------------------------------------------------------------------------------------


Après avoir affiché la clé publique avec :

```bash
cat ~/.ssh/id_ed25519.pub
```

👉 **Voici ce que vous devez faire ensuite :**

---

## 🔗 Étape suivante : Ajouter la clé SSH sur GitHub

### 1. 🔐 Copier la clé publique

Copiez **toute** la ligne affichée dans le terminal. Elle commence par `ssh-ed25519` ou `ssh-rsa` et se termine par votre email. Exemple :

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIEXEM... votre.email@example.com
```

---

### 2. 🌐 Aller sur GitHub

1. Connectez-vous à [https://github.com](https://github.com)
2. En haut à droite, cliquez sur votre **photo de profil** > **Settings**
3. Dans le menu de gauche, cliquez sur **"SSH and GPG keys"**
4. Cliquez sur le bouton **"New SSH key"**

---

### 3. ➕ Ajouter la clé

* **Title** : donnez un nom à la clé (ex : "Clé de mon PC portable").
* **Key** : collez la clé que vous avez copiée avec `cat`.

Cliquez sur **"Add SSH key"**.

---

## ✅ Étape finale : Tester la connexion SSH avec GitHub

Dans votre terminal, tapez :

```bash
ssh -T git@github.com
```

Si tout est bien configuré, vous verrez un message comme :


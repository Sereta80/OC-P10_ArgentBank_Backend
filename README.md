# 🏦 Argent Bank – Back-end (API)

API du projet 10 de la formation **Intégrateur web** d'OpenClassrooms. Elle est utilisée par le front-end : [OC-P10_ArgentBank-Frontend](https://github.com/Sereta80/OC-P10_ArgentBank-Frontend).

Ce dépôt contient aussi la **proposition de documentation Swagger pour la phase 2 (transactions)** : `swagger-transactions.yaml`.

## 🛠️ Technologies

- Node.js et Express
- MongoDB et Mongoose
- JSON Web Token (authentification)
- Swagger (documentation de l'API)

## 📋 Prérequis

- [Node.js](https://nodejs.org/) et npm
- [MongoDB Community Server](https://www.mongodb.com/try/download/community)

Vérifier les installations :

```bash
node --version
mongod --version
```

## 🚀 Installation et lancement

1. Cloner le dépôt et installer les dépendances :

```bash
git clone https://github.com/Sereta80/OC-P10_ArgentBank_Backend.git
cd OC-P10_ArgentBank_Backend
npm install
```

2. Démarrer MongoDB, dans un terminal à laisser ouvert :

```bash
mongod --dbpath <chemin/vers/votre/dossier/data/db>
```

3. Démarrer l'API, dans un second terminal à laisser ouvert :

```bash
npm run dev:server
```

L'API est disponible sur `http://localhost:3001`.

4. Au premier lancement, créer les deux utilisateurs de test, dans un troisième terminal :

```bash
npm run populate-db
```

## 👤 Comptes de test

| Utilisateur | Email | Mot de passe | Nom d'utilisateur |
|---|---|---|---|
| Tony Stark | `tony@stark.com` | `password123` | `Iron` |
| Steve Rogers | `steve@rogers.com` | `password456` | `Captain` |

## 📖 Documentation de l'API

### 🔐 Phase 1 – Utilisateur (implémentée)

Une fois l'API lancée, la documentation est disponible sur : `http://localhost:3001/api-docs` (fichier `swagger.yaml`).

Endpoints utilisés par le front-end :

| Méthode | Endpoint | Description |
|---|---|---|
| `POST` | `/api/v1/user/login` | Connexion, renvoie un token JWT |
| `GET` | `/api/v1/user/profile` | Récupère le profil de l'utilisateur connecté |
| `PUT` | `/api/v1/user/profile` | Modifie le profil de l'utilisateur connecté |

### 💳 Phase 2 – Transactions (proposition)

Le fichier `swagger-transactions.yaml` (Swagger 2.0) décrit les endpoints proposés. Ils ne sont pas implémentés dans ce dépôt. Pour les consulter, coller le contenu du fichier dans [Swagger Editor](https://editor.swagger.io/).

| Méthode | Endpoint | Description |
|---|---|---|
| `GET` | `/api/v1/user/accounts/{accountId}/transactions` | Transactions du mois en cours pour un compte |
| `GET` | `/api/v1/user/transactions/{transactionId}` | Détails d'une transaction |
| `PUT` | `/api/v1/user/transactions/{transactionId}` | Ajout ou modification de la catégorie et de la note |
| `DELETE` | `/api/v1/user/transactions/{transactionId}/note` | Suppression de la note |

Tous ces endpoints nécessitent un token JWT dans l'en-tête `Authorization: Bearer <token>`.

---

*Séréta THAI - Étudiante Intégratrice Web chez OpenClassrooms 2026-2027*

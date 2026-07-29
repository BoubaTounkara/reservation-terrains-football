# 🏟️ Système de Réservation de Terrains de Football

![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-MVC-512BD4?logo=dotnet&logoColor=white)
![Entity Framework](https://img.shields.io/badge/EF%20Core-SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-Paiement-635BFF?logo=stripe&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

Application web complète de réservation de terrains de football développée avec **ASP.NET Core 8 MVC**, avec paiement en ligne **Stripe**, authentification multi-rôles et intégration d'une API externe.

## 🎬 Démo

▶️ **Vidéo de présentation** : [https://youtu.be/eFgZHTiqPi4](https://youtu.be/eFgZHTiqPi4)

## 📋 Description

Cette application permet aux **clients** de réserver des créneaux horaires pour des terrains de football, aux **fournisseurs** de gérer leurs terrains et de consulter leurs revenus, et aux **administrateurs** de superviser l'ensemble du système.

## ✨ Fonctionnalités principales

### Pour les clients
- 🔍 Recherche avancée de terrains avec filtres (ville, type, date, plage horaire)
- 🛒 Panier de réservation
- 💳 Paiement sécurisé via Stripe
- 📅 Consultation des réservations et 🧾 historique des factures

### Pour les fournisseurs
- ➕ Ajout, modification et suppression de terrains
- 📊 Consultation des gains cumulés et suivi des revenus par terrain

### Pour les administrateurs
- 📊 Tableau de bord avec statistiques globales
- 👥 Gestion des utilisateurs (avec intégration API **DummyJSON**)
- 🏟️ Vue d'ensemble des terrains et 📋 gestion des réservations

## 🛠️ Stack technique

- **Backend** : ASP.NET Core 8.0 MVC
- **Base de données** : SQL Server + Entity Framework Core
- **Authentification** : ASP.NET Core Identity
- **Paiement** : Stripe API (`Stripe.net`)
- **Frontend** : Razor Views, Bootstrap 5, JavaScript
- **API externe** : DummyJSON (utilisateurs fictifs)

## 🚀 Installation

### Prérequis
- .NET 8.0 SDK
- SQL Server (LocalDB ou Express)
- Un compte Stripe (mode test) pour les paiements

### Étapes

```bash
# 1. Cloner le dépôt
git clone https://github.com/BoubaTounkara/reservation-terrains-football.git
cd reservation-terrains-football

# 2. Configurer les secrets (voir docs/CONFIGURATION_STRIPE.md)
cp appsettings.Template.json appsettings.json
#   puis renseigner vos clés Stripe dans appsettings.json (fichier non versionné)

# 3. Restaurer, créer la base et lancer
dotnet restore
dotnet ef database update
dotnet run
```

L'application est accessible sur `https://localhost:7186`.

> ⚙️ **Configuration détaillée de Stripe** : voir [docs/CONFIGURATION_STRIPE.md](docs/CONFIGURATION_STRIPE.md).
> 🧪 **Guide de tests complet** : voir [docs/GUIDE_TESTS.md](docs/GUIDE_TESTS.md).

## 👥 Comptes de test (démo locale)

| Rôle | Identifiant | Mot de passe |
|---|---|---|
| Admin | `admin@terrains.com` | `Admin123!` |
| Client | `client@terrains.com` | `Client123!` |
| Fournisseur | `fournisseur1@terrains.com` | `Fournisseur123!` |

> Comptes créés à l'initialisation de la base — valables uniquement en local.

**Cartes de test Stripe :** succès `4242 4242 4242 4242`, échec `4000 0000 0000 9995` (date future, CVC quelconque).

## 💰 Tarification

| Type de terrain | Prix par créneau (1h30) |
|---|---|
| 5-a-side | 35 $ |
| 7-a-side | 55 $ |
| 11-a-side | 90 $ |

## 🏗️ Structure du projet

```
├── Controllers/     # Contrôleurs MVC
├── Models/          # Modèles de données + ViewModels
├── Views/           # Vues Razor
├── Services/        # Services métier (Stripe, DummyJSON, ...)
├── Data/            # Contexte EF et initialisation de la base
├── Migrations/      # Migrations Entity Framework
├── wwwroot/         # Fichiers statiques (CSS, JS)
├── docs/            # Documentation, guides et rapport
└── appsettings.Template.json  # Modèle de configuration (à copier)
```

## 👨‍💻 Auteurs

- **Aboubacar Tounkara** — Développement Backend
- **Eli Daniel Senyo** — Développement Frontend

## 📄 Licence

Distribué sous licence **MIT** — voir [LICENSE](LICENSE). Projet initialement réalisé dans un cadre académique (Technologies du Commerce Électronique).

---

⚠️ Projet à des fins éducatives. Ne jamais utiliser de clés API réelles en production sans sécurisation appropriée.

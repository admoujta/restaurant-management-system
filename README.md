# RestauManager

Application web Symfony de gestion de restaurant, construite autour de trois espaces utilisateurs: administrateur, serveur et client. Le projet met en avant une architecture MVC avec Symfony, Doctrine ORM, Twig, un systeme d'authentification par roles et une gestion complete des reservations.

## Apercu

RestauManager simule le fonctionnement d'un restaurant:

- les clients consultent la carte, creent un compte et reservent une table;
- les serveurs suivent les reservations du jour, confirment ou annulent les demandes et gerent l'etat des tables;
- les administrateurs pilotent les tables, les plats, les menus, les utilisateurs et les reservations depuis un back-office.

Ce projet a ete pense comme une application full-stack presentable dans un portfolio: il montre la gestion des entites, des formulaires, des routes securisees, des fixtures, des migrations Doctrine et des vues Twig responsives basees sur Bootstrap.

## Fonctionnalites

- Authentification avec redirection selon le profil utilisateur.
- Gestion des roles `ROLE_ADMIN`, `ROLE_SERVEUR` et `ROLE_CLIENT`.
- Tableau de bord administrateur avec statistiques de reservations, tables et utilisateurs.
- CRUD administrateur pour les tables, plats, menus, utilisateurs et reservations.
- Espace serveur pour les reservations du jour, le statut des tables et la carte.
- Espace client pour la consultation de la carte, les reservations et le profil.
- API JSON pour rechercher les tables et creneaux disponibles.
- Page publique de presentation du restaurant et carte accessible sans connexion.
- Fixtures pour generer des comptes de demonstration, plats, menus, tables et reservations.

## Stack technique

| Couche | Technologie |
| --- | --- |
| Backend | PHP 8.2+, Symfony 7.4 |
| Templates | Twig, Bootstrap 5 |
| Base de donnees | PostgreSQL via Docker Compose |
| ORM | Doctrine ORM, Doctrine Migrations |
| Securite | Symfony Security Bundle |
| Donnees de demo | Doctrine Fixtures, Faker |
| Tests | PHPUnit |

## Structure principale

```text
src/
  Controller/        Controleurs publics, client, serveur, admin et API
  Entity/            Entites Doctrine: User, Reservation, RestaurantTable, Plat, Menu
  Form/              Formulaires Symfony
  Repository/        Requetes metier Doctrine
  DataFixtures/      Jeux de donnees de demonstration
templates/
  admin/             Back-office administrateur
  serveur/           Interface serveur
  client/            Espace client
  public/            Pages publiques
config/              Configuration Symfony, Doctrine et securite
migrations/          Historique des migrations Doctrine
```

## Installation locale

### Prerequis

- PHP 8.2 ou plus
- Composer
- Docker et Docker Compose, pour la base PostgreSQL
- Symfony CLI, recommande pour lancer le serveur local

### Demarrage

```bash
composer install
cp .env.example .env
docker compose up -d
php bin/console doctrine:database:create --if-not-exists
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load
symfony server:start
```

L'application sera disponible sur `http://127.0.0.1:8000`.

## Comptes de demonstration

Si les fixtures sont chargees, ces comptes peuvent etre utilises:

| Role | Email | Mot de passe | Acces |
| --- | --- | --- | --- |
| Admin | `admin@example.com` | `admin123` | `/admin/dashboard` |
| Serveur | `serveur@example.com` | `serveur123` | `/serveur/` |
| Client | `client@example.com` | `client123` | `/client/dashboard` |

Les fixtures principales creent aussi un compte `admin@restaurant.com` avec le mot de passe `admin123`.

## Routes utiles

| Page | URL |
| --- | --- |
| Accueil | `/` |
| Connexion | `/connexion` |
| Inscription | `/inscription` |
| Carte publique | `/carte` |
| Reservation publique | `/reserver` |
| Dashboard admin | `/admin/dashboard` |
| Gestion des tables | `/admin/tables` |
| Gestion des plats | `/admin/plats` |
| Gestion des menus | `/admin/menus` |
| Gestion des utilisateurs | `/admin/utilisateurs` |
| Gestion des reservations | `/admin/reservations` |
| Dashboard serveur | `/serveur/` |
| Reservations serveur | `/serveur/reservations` |
| Espace client | `/client/dashboard` |
| API tables disponibles | `/api/tables-disponibles?date=2026-06-01&heure=19:00&nbPersonnes=2` |
| Health check | `/status/health` |

## Commandes utiles

```bash
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load
php bin/console debug:router
php bin/phpunit
```

## Idees d'amelioration

- Ajouter des captures d'ecran dans un dossier `docs/screenshots`.
- Completer les tests fonctionnels des parcours admin, serveur et client.
- Ajouter l'envoi d'e-mails de confirmation pour les reservations.
- Ajouter une recherche avancee par date, capacite et statut.
- Preparer un deploiement avec variables d'environnement de production.

## Presentation portfolio

**RestauManager** est une application Symfony 7 de gestion de restaurant avec authentification multi-roles. Elle permet aux clients de reserver une table, aux serveurs de suivre les reservations et aux administrateurs de gerer la carte, les tables, les utilisateurs et les reservations. Le projet illustre une application web full-stack structuree avec Doctrine, Twig, formulaires Symfony, migrations, fixtures et routes securisees.

# Watson - Gestionnaire de Liens

Watson est une application web collaborative permettant de gérer, organiser et partager des liens intéressants avec des tags et une interface d'administration sécurisée.

## 🚀 Fonctionnalités

- **Affichage des liens** : Découvrez tous les liens disponibles avec pagination (15 liens par page)
- **Filtrage par tags** : Recherchez les liens associés à des tags spécifiques
- **Flux RSS** : Abonnez-vous aux 15 derniers liens via un flux RSS
- **Administration sécurisée** : Espace dédié pour gérer les liens et les utilisateurs
  - Ajouter, modifier et supprimer des liens
  - Gérer les utilisateurs du système
  - Associer des tags aux liens
- **Système d'authentification** : Connexion sécurisée avec chiffrement de mot de passe
- **Pagination** : Navigation fluide à travers les liens avec pagination

## 🛠️ Technologies utilisées

- **Framework** : Silex (micro-framework Symfony)
- **Template** : Twig
- **Base de données** : MySQL/MariaDB (avec Doctrine DBAL)
- **Frontend** : Bootstrap 3, jQuery
- **Sécurité** : Symfony Security Component
- **Validation** : Symfony Form Component

## 📋 Prérequis

- PHP 7.0 ou supérieur
- MySQL/MariaDB
- Composer
- Apache avec mod_rewrite activé

## 📦 Installation

1. **Cloner le repository**
```bash
git clone https://github.com/Alphayra/UEL313-Groupe4-S3.git
cd Watson
```

2. **Installer les dépendances**
```bash
composer install
```

3. **Configurer la base de données**
   - Importer le schéma SQL depuis `db/db.sql`
   - Configurer les identifiants dans `app/config/dev.php` ou `app/config/prod.php`

4. **Configurer Apache**
   - Pointer le `DocumentRoot` vers le dossier `web/`
   - Activer `mod_rewrite` : `a2enmod rewrite`
   - Ajouter un fichier `.htaccess` dans le dossier `web/` :
```apache
<IfModule mod_rewrite.c>
    Options -MultiViews
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^ index.php [QSA,L]
</IfModule>
```

5. **Relancer Apache**
```bash
sudo service apache2 restart
```

### Ajouter un lien
- Allez dans Admin → Onglet "Links" → Bouton "Add link"
- Remplissez le formulaire avec titre, URL, description et tags (séparés par des espaces)
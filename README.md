# Laravel + PrimeVue Starter Kit

## About

![Static Badge](https://img.shields.io/badge/Laravel%20-%20v12%20-%20%23f9322c) ![Static Badge](https://img.shields.io/badge/Inertia.js%20-%20v2%20-%20%236b46c1) ![Static Badge](<https://img.shields.io/badge/Vue.js%20-%20v3.5%20-%20rgb(66%20184%20131)>) ![Static Badge](<https://img.shields.io/badge/PrimeVue%20-%20v4%20-%20rgb(16%20185%20129)>) ![Static Badge](https://img.shields.io/badge/Tailwind%20CSS%20-%20v4%20-%20%230284c7)

A basic authentication starter kit using [Laravel](https://laravel.com/docs/master), [Intertia.js](https://inertiajs.com/), [PrimeVue](https://primevue.org/) components, and [Tailwind CSS](https://tailwindcss.com/).

> [!TIP]
> Do you need a separate Vue SPA front-end instead of using Inertia.js? Consider using the [PrimeVue SPA + Laravel API Starter Kit](https://github.com/connorabbas/laravel-api-primevue-starter-kit) instead.

## Resources

[🌐 **Demo Application**](https://demo.laravel-primevue-starter-kit.com/)

[📚 **Documentation**](https://connorabbas.github.io/laravel-primevue-starter-kit-docs/)


## 🚀 1. System Requirements

- **PHP >= 8.2**
- **Composer >= 2.0**
- **Node.js >= 22 & npm**
- **MySQL / PostgreSQL / SQLite**
- **Git**
- *(Optional)* WAMP / XAMPP for local hosting

---

## 📦 2. Installation

### 2.1 Clone the repository

```bash
git clone https://github.com/vorenus85/laravel-primevue-starter-kit
cd laravel-primevue-starter-kit
```

### 2.2 Install PHP dependencies
```bash
composer install
```

### 2.3 Create the **.env** file

```bash
cp .env.example .env
```

Then update the .env file with the correct database and application settings.

### 2.4 Generate application key

```bash
php artisan key:generate
```

### 2.5 Run migrations and seed the database

```bash
php artisan migrate --seed
```

## 🎨 3. Frontend Setup

```bash
npm install
```

The project use Vite

```bash
npm run dev     # development mode (HMR)
npm run build   # production build
```

## 🔧 4. Start Local Development

In your composer.json includes a dev script:

```bash
composer dev
```

This command runs the following in parallel:

- php artisan serve
- php artisan queue:listen
- npm run dev

Alternatively, you can run them manually:

```bash
php artisan serve
php artisan queue:listen
npm run dev
```

## 🌐 5. Local Domain Configuration (optional)

To access the project via a custom local domain (e.g. laravel-primevue-starter-kit.local):

### Edit your hosts file

```lua
127.0.0.1    laravel-primevue-starter-kit.local
```

### Create an Apache VirtualHost

```apache
<VirtualHost *:80>
    ServerName laravel-primevue-starter-kit.local
    DocumentRoot "C:/wamp64/www/git/laravel-primevue-starter-kit/public"

    <Directory "C:/wamp64/www/git/laravel-primevue-starter-kit/public">
        AllowOverride All
        Require all granted
        Options Indexes FollowSymLinks
    </Directory>
</VirtualHost>
```

### Update .env

```env
APP_URL=http://laravel-primevue-starter-kit.local
```

## 🧪 6. Run Tests

```bash
composer test
```

## 🧹 7. Useful Commands

| Command                            | Description                     |
| ---------------------------------- | ------------------------------- |
| `php artisan serve`                | Start Laravel dev server        |
| `php artisan migrate:fresh --seed` | Rebuild database with seed data |
| `php artisan cache:clear`          | Clear application cache         |
| `npm run dev`                      | Run frontend with HMR           |
| `npm run build`                    | Production frontend build       |
| `php artisan queue:listen`         | Start queue worker              |
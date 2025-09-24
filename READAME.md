# Laravel QA

A Q&A style web application built with **Laravel 6.x**.  
⚠️ Requires **PHP 7.4**.

---

## Requirements

- PHP 7.4
- Composer
- MySQL 5.7+ / 8.0
- PHP extensions: `pdo`, `pdo_mysql`, `mbstring`, `xml`, `zip`, `gd`, `bcmath`

> 💡 Tip: If you don’t want to install PHP 7.4 locally, you can run it inside **Docker** using the official `php:7.4-fpm` image.

---

## Setup

1. Clone the repository:
```bash

git clone <repo-url>
cd laravel-qa
```

2. Copy the environment file:
```bash

cp .env.example .env
```

3. Install dependencies:
```bash

composer install
```

4. Generate application key:
```bash

php artisan key:generate
```

5. Run migrations and seed demo data:
```bash

php artisan migrate --seed
```

6. Start the development server:
```bash

php artisan serve
```

The app will be available at [http://localhost:8000/register](http://localhost:8000/register).

---

## Demo Data

To reload example questions and answers:

```bash

php artisan db:seed
```

---

## Notes

- This is an **old project originally built years ago**.  
- It has been updated and made functional again with only a few small changes.  
- The codebase is still stable and runs correctly on **Laravel 6.x with PHP 7.4**.

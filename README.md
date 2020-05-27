# RefreshDatabase trait issue

## Installation

Launch the mysql container and run `php artisan test` twice

```shell
git@github.com:StevePorter92/refresh-database-issue.git
docker-compose up -d
php artisan test
php artisan test
```

See the following error:

```
SQLSTATE[42S01]: Base table or view already exists: 1050 Table 'tests' already exists (SQL: create table `tests` (`id` bigint unsigned not null auto_increment primary key, `created_at` timestamp null, `updated_at` timestamp null) default character set utf8mb4 collate 'utf8mb4_unicode_ci')
```

## Description

The `Illuminate\Foundation\Testing\RefreshDatabase` trait only wipes the main database connection.

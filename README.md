# laravel-uuid
Simply create Eloquent Models & database tables with UUID/GUID primary keys.

# Installation

``` 
composer require michalkortas/laravel-uuid
```

# Usage

Add uuid as primary key in your table migration.

```php
Schema::create('customers', function (Blueprint $table) {
    $table->uuid('id')->primary();
});
```

Add trait to your Eloquent Model.

```php
<?php

namespace AppModels;

use michalkortas\LaravelUuid\traits\HasUuid;
use Illuminate\Database\Eloquent\Model;

class Customers extends Model
{
    use HasUuid;
}
```

Now, when you run migrations, newly created table has datatype ID as CHAR(36). UUID will be inserted automatically with ```Model::create()``` method.

![ID datatype - UUID - CHAR(36)](https://webroad.pl/wp-content/uploads/2021/02/uuid-tabela.png)

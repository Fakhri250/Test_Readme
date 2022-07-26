###### Nama : Naufal F.Z
###### Kelas : XII RPL-2
###### No.Absen : 14

# Modul 1

### Soal
#### 1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.
#### 2. Buatlah projek pertama laravel dengan nama projek “penjualan” dan tampilkan dalam browser.
```
composer create-project laravel/laravel penjualan
```

# Modul 2

### Soal
##### 1. Buatlah migration tabel kategori dengan menggunakan teknik yang telah di pelajari dalam 
modul ini.

### Langkah Pertama
ketik kode dibawah pada terminal
```
php artisan make:migration create_kategori_table
```

#### Langkah Kedua
Selanjutnya buka folder diatas lalu isi kode seperti dibawah ini
```
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('kategori', function (Blueprint $table) {
            $table->id();
            $table->string('nama');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('kategori');
    }
};
```

#### Langkah Ketiga
Selanjutnya ketik kode dibawah ini pada terminal anda
```
php artisan migrate
```

#### 2. Berikan data dengan menggunakan seeder yang telah anda pelajari pada modul ini

#### Langkah Pertama
Masukkan kode dibawah pada terminal anda
```
php artisan make:seeder KategoriTableSeeder
```
#### Langkah Kedua
Selanjutnya buka folder diatas kemudian masukkan seperti dibawah ini
```
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use DB;

class kategoriTableSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategori')->insert(array(
            [
                'nama' => 'Perlengkapan Sekolah',
            ],
            [
                'nama' => 'Komputer',
            ],
            [
                'nama' => 'Sabun',
            ],
            [
                'nama' => 'Accesories',
            ],
            [
                'nama' => 'ATK',
            ],
        ));
    }
}
```
#### Langka Ketiga
Kemudian masukkan kode dibawah ini didalam folder **DatabaseSeeder.php**
```
<?php

namespace Database\Seeders;

// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    /**
     * Seed the application's database.
     *
     * @return void
     */
    public function run()
    {
        $this->call(kategoriTableSeeder::class);
        // \App\Models\User::factory(10)->create();

        // \App\Models\User::factory()->create([
        //     'name' => 'Test User',
        //     'email' => 'test@example.com',
        // ]);
    }
}

```



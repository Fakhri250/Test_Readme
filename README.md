###### Nama : Naufal F.Z
###### Kelas : XII RPL-2
###### No.Absen : 14

# Modul 1

### Soal
1. Lakukan proses instalasi framework laravel kedalam folder dengan nama masing-masing.
2. Buatlah projek pertama laravel dengan nama projek “penjualan” dan tampilkan dalam browser.
```
composer create-project laravel/laravel penjualan
```

# Modul 2

### Soal
1. Buatlah migration tabel kategori dengan menggunakan teknik yang telah di pelajari dalam 
modul ini.

#### Langkah Pertama
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

Langkah Kedua
```
php artisan migrate
```
2. Berikan data dengan menggunakan seeder yang telah anda pelajari pada modul ini
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

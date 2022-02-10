# crudlaravel
cek laravel create
cek php artisan ser
buat database (sesuaikan nama)
ganti .env databse name (sesuaikan nama)
terminal (php artisan make:model (Employee) -mc
remake migration
        $table->id();
            $table->string('nama');
            $table->enum('jeniskelamin',['cowo','cewe']);
            $table->integer('notelp');
            $table->timestamps();
php artisan migrate
cek controler
REMAKE web.php
use App\Http\Controllers\EmployeeController;
Route::get('/pegawai', [EmployeeController::class, 'index'])->name('pegawai');
remake controler(employee)
 public function index()
    {
        return view('datapegawai');
    }
    jadi  
    public function index()
    {
        $data =  Employee::all();
        return view('datapegawai', compact('data'));
    }
    
    buat view datapegawai.blade.php
    <!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1 class="text-center mb-4 ">Data Pegawai</h1>
    <div class="container">
         <button type="button" class="btn btn-success">Tambah +</button>
        <div class="row">
             <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Nama</th>
      <th scope="col">Jenis Kelamin</th>
      <th scope="col">No Telpon</th>
      <th scope="col">Aksi</th>
    </tr>
  </thead>
  <tbody>
      @foreach ($data as $row)
        
    <tr>
      <th scope="row">{{ $row->id }}</th>
      <td>{{ $row->nama}}</td>
      <td>{{ $row->jeniskelamin}}</td>
      <td>0{{$row->notelp}}</td>
      <td>
          <button type="button" class="btn btn-info">Edit</button>
          <button type="button" class="btn btn-danger">Delete</button>
      </td>
       

    </tr>
   
      @endforeach
  </tbody>
</table>
        </div>
    </div>
   
    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.10.2/dist/umd/popper.min.js" integrity="sha384-7+zCNj/IqJ95wo16oMtfsKbZ9ccEh31eOz1HGyDuCQ6wgnyJNSYdrPa03rtR1zdB" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.min.js" integrity="sha384-QJHtvGhmr9XOIpI6YVutG+2QOK9T+ZnN4kzFN1RtK3zEFEIsxhlmWl5/YESvpZ13" crossorigin="anonymous"></script>
    -->
  </body>
</html>
    
    
    REMAKE SEEDER EMPLOYER
     public function run()
    {
        DB::table('employees')->insert([
            'nama' => 'viki maynaki',
            'jeniskelamin' => 'cowo',
            'notelp' => '081294789727',
        ]);
    }
    php artisan db:seed --class=EmployeeSeeder


tambah data

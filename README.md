#PHPStorm Laravel live templates

##How to use
Grab the `Laravel.xml` file and put it to PHPStorm templates dir. 

* For mac: `~/Libraries/Preferences/WebIde70/templates`
* For win: `%USERPROFILE%\.WebIde70\config\templates`
* For linux: `~/.WebIde70/config/templates`

##Included

* [Resource controller](#resource-controller)
* [Model](#model)
* [Migration](#migration)
* [Seeder](#seeder)
* [Service Provider](#service-provider)

###Resource controller
abbr: `resource`
```php
class $CLASSNAME$ extends \BaseController {

	/**
	 * Display a listing of the resource.
	 *
	 * @return Response
	 */
	public function index()
	{
        return \View::make('$COLL$.index');$END$
	}

	/**
	 * Show the form for creating a new resource.
	 *
	 * @return Response
	 */
	public function create()
	{
        return \View::make('$COLL$.create');
	}

	/**
	 * Store a newly created resource in storage.
	 *
	 * @return Response
	 */
	public function store()
	{
		//
	}

	/**
	 * Display the specified resource.
	 *
	 * @param  int  $id
	 * @return Response
	 */
	public function show($id)
	{
        return \View::make('$COLL$.show');
	}

	/**
	 * Show the form for editing the specified resource.
	 *
	 * @param  int  $id
	 * @return Response
	 */
	public function edit($id)
	{
        return \View::make('$COLL$.edit');
	}

	/**
	 * Update the specified resource in storage.
	 *
	 * @param  int  $id
	 * @return Response
	 */
	public function update($id)
	{
		//
	}

	/**
	 * Remove the specified resource from storage.
	 *
	 * @param  int  $id
	 * @return Response
	 */
	public function destroy($id)
	{
		//
	}

}
```

###Model
abbr: `model`
```php
use Eloquent;
use Illuminate\Database\Eloquent\SoftDeletingTrait;

class $CLASSNAME$ extends Eloquent {
    use SoftDeletingTrait;
    
    public $timestamps = true;
    
    // Fields that are guarded from mass assignment
	//protected $guarded = array('id');
	
	// Fields that are opened for mass assignment
	protected $fillable = array();

	protected $dates = ['deleted_at'];
}
```

###Migration
Migration for table creation, but with table altering included under comments

abbr: `migrate`
```php
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;

class $CLASSNAME$ extends Migration {

	/**
	 * Run the migrations.
	 *
	 * @return void
	 */
	public function up()
	{
	    // create table
	    \Schema::create('$TABLENAME$', function(Blueprint $table) {
            $table->increments('id');
            $END$
            $table->timestamps();
        });
            		
		/*
		// modify table
		\Schema::table('$TABLENAME$', function(Blueprint $table) {
			// alter
		});
		*/
	}

	/**
	 * Reverse the migrations.
	 *
	 * @return void
	 */
	public function down()
	{
	    // drop table
	    \Schema::drop('$TABLENAME$');
	    
	    /*
	    // modify table
		\Schema::table('$TABLENAME$', function(Blueprint $table) {
			// alter
		});
		*/
	}

}
```

###Seeder
abbr: `seed`
```php
class $CLASSNAME$ extends \Seeder {

	public function run()
	{
	    $data = array(
	        $END$
	    );
	    
	    // DB::table('$TABLE$')->truncate();
	    // DB::table('$TABLE$')->insert($data);
	}

}
```

###Service Provider
abbr: `sp`
```php
use Illuminate\Support\ServiceProvider;

class $CLASSNAME$ extends ServiceProvider {

    /**
     * Register the service provider.
     *
     * @return void
     */
    public function register()
    {
        $END$// TODO: Implement register() method.
    }

    /**
     * Bootstrap the application events.
     *
     * @return void
     */
    public function boot()
    {
        parent::boot();
    }

    /**
     * Get the services provided by the provider.
     *
     * @return array
     */
    public function provides()
    {
        return parent::provides();
    }

    /**
     * Get the events that trigger this service provider to register.
     *
     * @return array
     */
    public function when()
    {
        return parent::when();
    }


}
```

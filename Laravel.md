* Search condition with query function in laravel

    $search = $request->query('search');

    $users = User::query();

    $users->when($request->query('search'), function ($builder, $search) {
        $builder->whereRaw("CONCAT(name, ' ', email) LIKE '%$search%'");
    });
    $users->whereIn('user_role', [1, 2]);
    $getAdmins = $users->paginate(10);

    $adminCount = DB::table('users')
                ->whereIn('user_role', [1, 2])
                ->count();      
                return view('admin.profile.all_admin', compact('getAdmins','adminCount'));



* Model Elqueunt method using INSERT 

 $customer       = new Customer;
 $customer->name = $request->name;
 $customer->save();

 Model Elqueunt method using update

 $customer        = Customer::find(1)
 $customer->name  = $request->name;
 $customer->save();


* Model Elquent using SELECT method

$customer = Customer::where('','')->orwhere('','')->get();


HOW TO CORE ENABLE ERROR SOLVE IN LARAVEL

STEP 1: Php artisan make:middleware cors

STEP2: APP/HTTP/KERNEL INSIDE ADD LINE IN MIDDL WARE
 \App\Http\Middleware\Cors::class,
 
STEP 3: add code inside cors.php in handle function 

        $response = $next($request);
        $response->headers->set('Access-Control-Allow-Origin' , '*');
        $response->headers->set('Access-Control-Allow-Methods', 'POST, GET, OPTIONS, PUT, DELETE');
        $response->headers->set('Access-Control-Allow-Headers', 'Content-Type, Accept, Authorization, X-Requested-With, Application');

        return $response; 








* Model Elquent using DELETE method
$customer = Customer::find(1);
$customer->delete();

* Laravel provide all method are lower camel case
   ->findOrFail();
   ->paginate();
   ->routeIs();
   ->isMethod

   *LARAVEL ELQUENT QUERY INSERT UPDATE DELETE

   $user = User::create([
                'name' =>$request->name
           ]);

           
   $user = User::where('id',$id)->update([
                'name' =>$request->name
           ]);

  $delete = User::where('',$id)->delete();

  * LARAVEL First, find, firstOrCreate  METHOD IN RETURN ONE ROW 
    $user = User::where('id',$request->id)->first();

    $user = user::find();

    $user = User::firstOrCreate([
        'name' =>$request->name;
    ]);

    * LARAVEL TURNARY OPERATOR IN ONE LINE 
    {{  ucfirst($user->name) ? ucfirst($user->name): 'NA'  }}

    * LARAVEL IN GET QUERY  IN SQL 
        DB::enableQueryLog();
        query
        dd(DB::getQueryLog());

    * LARAEL JOIN QUERY DB

    $saveditems  = DB::table('saved_videos')
                    ->join('users', 'users.id', '=', 'saved_videos.fk_user_id')
                    ->select('saved_videos.fk_user_id', 'users.*')
                    ->groupBy('saved_videos.fk_user_id')
                    ->paginate(20);


* Lavevel dump() function very usefull when get return query

$saveditems  = DB::table('saved_videos')
                    ->join('users', 'users.id', '=', 'saved_videos.fk_user_id')
                    ->select('saved_videos.fk_user_id', 'users.*')
                    ->groupBy('saved_videos.fk_user_id')
                    ->dump()
                    ->paginate(20);

 

CHAINING METHOD USING whereRow query
$posts = Post::query();
$posts->whereRow("SELEC DATE(start_challenge_at BETWEE DATE_ADD( DATE(NOW() ), INTERVAL -7 DAY) AND DATE(NOW() )");
$getPosts = $posts->get();


---------------------------

CRON JOB IN LARAVEL
      step 1: php artisan make:command DemoCron --command=demo:cron 
               file created:   app/Console/Commands/DemoCron.php

      step2: app/Console/Kernel.php
        add cmd:
                    protected $commands = [
                        Commands\DemoCron::class,
                    ];
       step3: php artisan schedule:run

    manully working per minitue working job
 CRON JOB IN AWS COMMDD
 step1: RUN COMMAND : sudo crontab -e  

 step2: * * * * * cd /var/www/html/btc

 

LARAVEL IN TRY CATCH USING 
try{
    try your code
}catch(\Exception $e)
{
    return redirect()->back()->with('true',$e->getMessage());
}




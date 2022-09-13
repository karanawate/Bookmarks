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




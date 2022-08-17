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


 




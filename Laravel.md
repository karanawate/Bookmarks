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



* Elqueunt method using INSERT 

 $customer       = new Customer;
 $customer->name = $request->name;
 $customer->save();

 Elqueunt method using update

 $customer        = Customer::find(1)
 $customer->name  = $request->name;
 $customer->save();


$customer = Customer::where('','')->orwhere('','')->get();


$customer = Customer::find(1);
$customer->delete();




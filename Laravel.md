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
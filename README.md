# laravel-pagination

Very simple code to implement pagination for laravel 5.3.4.
#Step 1. Use DB;  in your controller file.

#Step 2. Route file
Route::get('/pagination', 'AbcController@pagination');

#Step 3.  Function in controller
public function pagination()
	{
			

		$users = DB::table('user')->paginate(2);
        return view('pagination', ['users' => $users]);
	}

#Step 4. In view file
<div class="container">
    @foreach ($users as $user)
        {{ $user->name }}
    @endforeach
</div>

{{ $users->links() }}

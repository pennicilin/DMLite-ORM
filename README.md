# DMLite-ORM

> Since I've switched to [Laravel](https://laravel.com/) at my job, I won't have time to maintain this project; at least not in the near future. Feel free to fork it! Or even better, [use Laravel's Eloquent ORM](https://vkbansal.me/blog/using-eloquent-outside-laravel/) in CI3 (you can load it easily if using [composer-enabled CI3](http://forum.codeigniter.com/thread-64487.html)).

DataMapper-like ORM for CodeIgniter 3

This project is an attempt of making an ORM similar to DataMapper ORM which previously could be downloaded from <http://datamapper.wanwizard.eu>

DataMapper ORM is not being maintained/developed for a while now and it's not working with CI3. Well, not without some heavy hacking anyway. Even in CI2 you had to modify CI files to make it work, meh. Its git repository is deleted and it can't be downloaded anymore (officially). Nevertheless, it was my favorite ORM for CI2 and it's the main reason this project exists.

DMLite ORM is not, and probably will never be as flexible or as smart as DataMapper was. Not without your help. Join me and help me develop it into something superb.

## How to set it up?

Simply, download `MY_Model.php` from `application/core/` folder and place it in your project. That's the only file you  need. Find out more in this project's [Wiki](https://github.com/avramovic/DMLite-ORM/wiki).

## Show me example!

Sure, here it is:

```php
<?php
/* CI controller code */
   
//create author
$author = new Author();
$author->name = "Friedrich Nietzsche";
$author->dob = 1844;
$author->save();
   
//create book and save it along with it's author
$book = new Book();
$book->title = "Also sprach Zarathustra";   
$book->isbn = 9789562919760;
$book->year = 1883;
$book->save(array($author));

?>
```

For more examples check out the [Wiki](https://github.com/avramovic/DMLite-ORM/wiki)!

## What's done?

* fetching results with `where`, `or_where`, `where_in`, `or_where_in`, `where_not_in` and `or_where_not_in`
* fetching results with `where_related`, `or_where_related`, `where_in_related`, `or_where_in_related`, `where_not_in_related` and `or_where_not_in_related`
* standard [CI3 Query Builder](http://www.codeigniter.com/userguide3/database/query_builder.html) functions
* one-to-many and many-to-many relationships
* saving with relationships
* including related data into resultset
* deleting single object, set of objects or relationships only
* fetching with deep relationships

## What's yet to be done?

* saving join fields in many-to-many relationships
* querying by join fields
* including join fields into resultset
* `get_paged` to simply paginate over a result set

If you have idea please submit it as an issue. Pull requests are welcome.

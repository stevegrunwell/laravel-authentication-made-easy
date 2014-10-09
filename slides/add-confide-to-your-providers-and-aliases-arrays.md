##  Add Confide to your 'providers' and 'aliases' arrays

<p class="title">In app/config/app.php:</p>

```diff
   'providers' => array(
      ...
      'Illuminate\View\ViewServiceProvider',
      'Illuminate\Workbench\WorkbenchServiceProvider',
+     'Zizaco\Confide\ServiceProvider',
   ),

   'aliases' => array(
     ...
     'Validator'  => 'Illuminate\Support\Facades\Validator',
     'View'       => 'Illuminate\Support\Facades\View',
+    'Confide'    => 'Zizaco\Confide\Facade',
   ),
```
##  Update the User model

```diff
  <?php

  use Zizaco\Confide\ConfideUser;
  use Zizaco\Confide\ConfideUserInterface;

  class User extends Eloquent implements ConfideUserInterface
  {
-     use ConfideUser;
+     use ConfideUser, HasRole;
  }
```

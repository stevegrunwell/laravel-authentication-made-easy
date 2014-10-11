##  Check for permissions instead of roles

* Rather than assume what permissions each role has, it's usually better to check for permissions in your routes and templates
* Makes maintenance easier as a new role doesn't automatically mean updating all your permission checks
* Permissions use slugs ("assemble_blocks") rather than strings that can have spaces ("Assemble blocks")
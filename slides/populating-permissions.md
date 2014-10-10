<section>
<h2>Populating permissions</h2>

<pre><code class="php">$assemble = new Permission;
$assemble->name = 'assemble_blocks';
$assemble->display_name = 'Assemble blocks';
$assemble->save();</code></pre>
</section>

<section>
<h2>Populating (more) permissions</h2>

<pre><code class="php">$dream = new Permission;
$dream->name = 'dream_big';
$dream->display_name = 'Dream BIG!';
$dream->save();</code></pre>
</section>

<section>
<h2>Creating roles and assigning permissions</h2>

<pre><code class="php">$construction_worker = new Role;
$construction_worker->name = 'Average construction worker';
$construction_worker->save();

$construction_worker->perms()->sync([$assemble->id]);</code></pre>
</section>

<section>
<h2>Creating a more privileged role</h2>

<pre><code class="php">$master_builder = new Role;
$master_builder->name = 'Master Builder';
$master_builder->save();

$master_builder->perms()->sync([$assemble->id, $dream->id]);</code></pre>
</section>

<section>
<h2>Wait, what?</h2>

<strong>Average construction worker</strong>

<ul>
  <li>assemble_blocks</li>
</ul>

<strong>Master Builder</strong>

<ul>
  <li>assemble_blocks</li>
  <li>dream_big</li>
</ul>
</section>

<section>
<h2>Assigning a role to a user</h2>

<pre><code class="php">$user = User::where('username', '=', 'emmet')->first();

// Attach a specific ID
$user->roles()->attach($master_builder->id);

// OR...

// attachRole() can take a Role object, array, or ID
$user->attachRole($master_builder);</code></pre>
</section>

<section>
<h2>Now you have a new Master Builder!</h2>
<img src="assets/lego-awesome.gif" alt="Benny the Astronaut is excited!" />
</section>
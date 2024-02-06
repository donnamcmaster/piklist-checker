Class Piklist_Checker 
-
This class file is intended for use by WordPress plugins that rely on the Piklist plugin, in order to verify that Piklist is installed and activated. 

Piklist is no longer supported and the official repo is closed (read-only). This class file has an error that originally only generated a warning but becomes fatal when combined with recent versions of Gravity Forms (see details below). So I downloaded the source from https://github.com/piklist/piklist/blob/b71d6d5ce73cdd22b96b6642d18588e9fc88e967/.wordpress-org/class-piklist-checker.php and am updating it with a fix. 

For more information about Piklist_Checker, see the archived Piklist documentation: 
https://github.com/piklist/docs/blob/master/getting-started/piklist-checker/index.html

Problem Example
-
<pre>
PHP Notice:  Trying to access array offset on value of type null in /srv/public/wp-content/plugins/wp-helpers/wp-helpers.php on line 132
PHP Fatal error:  Uncaught ArgumentCountError: Too few arguments to function Piklist_Checker::show_message(), 0 passed in /srv/public/wp-content/plugins/gravityforms/common.php on line 5720 and at least 1 expected in /srv/public/wp-content/plugins/wp-helpers/includes/class-piklist-checker.php:211
Stack trace:
#0 /srv/public/wp-content/plugins/gravityforms/common.php(5720): Piklist_Checker::show_message()
#1 /srv/public/wp-includes/class-wp-hook.php(324): GFCommon::find_admin_notices('')
#2 /srv/public/wp-includes/class-wp-hook.php(348): WP_Hook->apply_filters(NULL, Array)
#3 /srv/public/wp-includes/plugin.php(517): WP_Hook->do_action(Array)
#4 /srv/public/wp-admin/admin-header.php(163): do_action('admin_head')
#5 /srv/public/wp-admin/admin.php(239): require_once('/srv/users/sofa...')
#6 {main}
  thrown in /srv/public/wp-content/plugins/wp-helpers/includes/class-piklist-checker.php on line 211
</pre>

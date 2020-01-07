# Wordpress-Knowledgebase
Snippets and code for wordpress development

```
//To check whether or not the current user has any of the specified roles, include this function in your plugin or theme’s functions.php file:

function check_user_role($roles, $user_id = null) {
	if ($user_id) $user = get_userdata($user_id);
	else $user = wp_get_current_user();
	if (empty($user)) return false;
	foreach ($user->roles as $role) {
		if (in_array($role, $roles)) {
			return true;
		}
	}
	return false;
}

// Once this function is included, you can call it like so:

if (check_user_role(array('author','editor','custom_role'))) {
	// do stuff for user
}

// Also, if you want to check a specific user ID, you can use the second parameter:

if (check_user_role(array('author','editor','custom_role'), 177)) {
	// do stuff for user ID 177
}

```

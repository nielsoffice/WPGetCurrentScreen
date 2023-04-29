# WPGetCurrentScreen
Get WordPress Admin Current Screen or Current admin page base on current URL

```PHP
/*
PAGE               $SCREEN_ID           FILE
-----------------  -------------------  -----------------------
Media Library      upload               upload.php
Comments           edit-comments        edit-comments.php
Tags               edit-post_tag        edit-tags.php
Plugins            plugins              plugins.php
Links              link-manager         link-manager.php
Users              users                users.php
Posts              edit-post            edit.php
Pages              edit-page            edit.php
Edit Site: Themes  site-themes-network  network/site-themes.php
Themes             themes-network       network/themes
Users              users-network        network/users
Edit Site: Users   site-users-network   network/site-users
Sites              sites-network        network/sites

*/

/**
 * Run code on the admin widgets page
 */
add_action( 'current_screen', 'wpdocs_this_screen' );
function wpdocs_this_screen() 
{

    $currentScreen  = get_current_screen();
    
    if( $currentScreen->id === "edit-comments" ) 
    {
        // Run some code, only on the admin edit-comments page admin back end wordpress
		echo "Plugins ";
    }

}

```

<br />Reference: 
<br />https://developer.wordpress.org/reference/functions/get_current_screen/
<br />https://wordpress.stackexchange.com/questions/136058/how-to-remove-admin-menu-pages-inserted-by-plugins

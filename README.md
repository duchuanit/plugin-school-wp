# plugin-school-wp
Plugin cho Wordpress

A. File Index
/*
Plugin Name: First Plugin
Description:
Version: 1
Author: LNDH
Author URI: https://duchuanblog.com
*/
add_action('admin_menu','sbc_menu');
function sbc_menu()
{
    // Page title - Menu title
	add_menu_page('Theme page title', 'First-plugin', 'manage_options', 'theme-options', 'wps_theme_func');
	add_submenu_page( 'theme-options', 'Settings page', 'Settings menu label', 'manage_options', 'theme-op-settings', 'wps_theme_func_settings');
	add_submenu_page( 'theme-options', 'FAQ page', 'FAQ menu label', 'manage_options', 'theme-op-faq', 'wps_theme_func_faq');
}

//Load file
define('ROOTFILE', plugin_dir_path(__FILE__));// Xac dinh ten và duong dan file
require_once(ROOTFILE . 'fa.php');
require_once(ROOTFILE . 'fb.php');
require_once(ROOTFILE . 'fc.php');

B. File List
global $wpdb;
        $table_name = $wpdb->prefix . "school";

		$rows = $wpdb->get_results("SELECT id,name from $table_name");
		foreach ($rows as $row) { 
			echo $row->id; 
			echo $row->name;
			echo '<br/>';
		}
    
  C. File Update
  


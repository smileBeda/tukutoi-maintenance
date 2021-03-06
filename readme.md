# TukuToi Maintenance ![ClassicPress Plugin: Required CP Version](https://img.shields.io/badge/dynamic/json?color=%23057f99&label=classicpress&prefix=v&query=%24.data.minimum_cp_version&url=https%3A%2F%2Fdirectory.classicpress.net%2Fapi%2Fplugins%2Ftukutoi-maintenance) ![WordPress Plugin: Tested WP Version](https://img.shields.io/wordpress/plugin/tested/tkt-maintenance)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=TukuToi_tukutoi-maintenance&metric=bugs)](https://sonarcloud.io/dashboard?id=TukuToi_tukutoi-maintenance) [![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=TukuToi_tukutoi-maintenance&metric=vulnerabilities)](https://sonarcloud.io/dashboard?id=TukuToi_tukutoi-maintenance) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=TukuToi_tukutoi-maintenance&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=TukuToi_tukutoi-maintenance) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=TukuToi_tukutoi-maintenance&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=TukuToi_tukutoi-maintenance) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=TukuToi_tukutoi-maintenance&metric=security_rating)](https://sonarcloud.io/dashboard?id=TukuToi_tukutoi-maintenance)

Enable and Control a Custom Maintenance Mode for your WordPress Website.

TukuToi Maintenance allows you to setup and control a Custom "Under Maintenance" or "Coming Soon" Screen for your WordPress Website.

The Plugin is lightweight and has a Settings Screen allowing you to control all aspects of the Maintenance Screen from the WordPress backend.

You will be able to control the image (or color) of the Maintenance Screen, add a CountDown and a Custom Heading, as well as a Custom message to the screen.
You can control the request status (defaults to 401 temporarily unavailable) and the time for when the site will be back.
This is useful to tell Crawling bots when to start re-crawling your website.

## Installation

1. Upload the Plugin files to the `/wp-content/plugins/` directory.
1. Activate the plugin through the 'Plugins' menu in WordPress.
1. Setup and control the Settings in the native WordPress Settings > Reading screen, under the newly added TukuToi Maintenance Section

## Frequently Asked Questions

### How big should the Image used for the Maintenance Screen be?

The optimal (website) background image size is 1920 x 1080 pixels with a 16:9 ratio, the dpi (dots per inch) should be at least 72.
However you are free to upload bigger or smaller sizes, as you wish.

### How big should the Logo Image used for the Maintenance Screen be?

It should ideally be at least 300px square.

### Can I still access the WP Admin when activating the Maintenance Mode?

Of course! You will have to navigate to the native `/wp-login.php` URL of your website and will be able to login.
For Administrators, the Front End will not show the Maintenance Mode. It will continue to show your website, in order to allow you to control your development.

### Can I Fully Customize the Maintenance Mode Template?

Of course! You can either use the Plugin settings to customize the template, or, you can also load your 100% custom PHP template, if you wish. To do so, just pass your Custom PHP template to the `tkt_mtn_template_path` filter which the plugin provides.

Example (assuming you store the template in your Theme's `template-parts/post/` folder):
```
add_filter( 'tkt_mtn_template_path', 'load_my_own_template', 10, 1 );
function load_my_own_template( $template_path ){

	$template_path = get_template_directory() .'/template-parts/post/custm_template.php';//Load your own template.

	return $template_path;

}
```

You can take a look at the Plugin's Template in `tkt-maintenance/public/partials/tkt-maintenance-public-display.php` file to get a kickstart for your own Template.
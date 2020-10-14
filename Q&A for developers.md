**Table of contents**

* [Auto-update](#section-1-auto-update)
* [Image editor](#section-2-image-editor)
* [Block Directory Repository](#section-3-block-directory-repository)
* [Block Patterns](#section-4-block-patterns)
* [Gutenberg Update](#section-5-gutenberg-update)
* [Lazy-loading](#section-6-lazy-loading)
* [XML Sitemaps](#section-7-xml-sitemaps)
* [jQuery](#section-8-jquery)

## SECTION 1. Auto-update

### Key information and links for developers on auto-updates in 5.5

1. Where can I find more information for developers about auto-update for themes and plugins?

Support-related information about auto-updates on plugins and themes
https://wordpress.org/support/article/plugins-themes-auto-updates/ 

Dev notes on controlling plugin and theme auto-update email notifications and site health information in WordPress release  5.5 
https://make.wordpress.org/core/2020/07/30/controlling-plugin-and-theme-auto-update-email-notifications-and-site-health-infos-in-wp-5-5/

Field Notes on Auto-Update for WordPress release 5.5
https://make.wordpress.org/core/2020/07/15/controlling-plugin-and-theme-auto-updates-ui-in-wordpress-5-5/ 

Check the current WordPress requirements on this page. https://wordpress.org/about/requirements/

Use the PHP Compatibility plugin to check if your plugin is compatible with the variety of PHP versions that sites may be using. https://wordpress.org/plugins/php-compatibility-checker/

### Notifications about updates

2. If there is a plugin or theme update available and auto-updates are enabled, will it still show that the theme needs to be updated? 

Yes, you will be able to view this in your dashboard.

3. What kind of emails from the dashboard will I receive when my plugins and themes are auto updated?

When a plugin or theme is automatically updated, the admin will receive an email notification with the names of the plugin or theme which has been updated and their respected version number. This is more to keep site owners informed of the updates being applied on their sites? This will help the administrator of the website to decide if they want to manually rollback a version if an update leads to any problems on the site.

4. I am trying to switch auto-update off but it doesn't work. Why is this?

Some plugin authors have made autoupdate of their plugins mandatory. 
https://core.trac.wordpress.org/browser/tags/5.5/src/wp-admin/includes/class-wp-plugins-list-table.php?marks=1096-1098#L1094

### Timings of updates

5. I enabled auto-update, but it seems to schedule the process at some time in the future. Can I pick an alternative time? 

You currently are not able to specify a time to run auto-updates of plugins and themes. By default, WordPress checks for available updates every 12 hours.

6. I am concerned about Auto Updating as I run a very busy site. What can I do? 

You can blanket opt out of all future installed plugin and theme auto updates using the new filters introduced: 
```
//Disable all plugin auto-updates.
add_filter( 'auto_update_plugin', '__return_false' );
```
```
// Enable all theme auto-updates.
add_filter( 'auto_update_theme', '__return_false );
```

You can remove the new admin UI using the following filters, which disabled the ability to turn auto updates on or off: 

```
// Disable plugins auto-update UI elements.
add_filter( 'plugins_auto_update_enabled', '__return_false' );
```
```
// Disable themes auto-update UI elements.
add_filter( 'themes_auto_update_enabled', '__return_false' );
```

There are plugins available on the WordPress.org plugin repository that can help you with controlling all types of updates. 

### Issues following an update

7. How can I debug a problem caused by an auto-update?

There isn’t a way to detect which plugin caused a conflict. It is important to only opt into the auto-update of plugins or themes you are sure will not cause a conflict.

A good place to start debugging if you run into issues is the Site Health dashboard introduced in WordPress release 5.1 
https://make.wordpress.org/core/2019/01/14/php-site-health-mechanisms-in-5-1/

Support information on debugging in WordPress
https://wordpress.org/support/article/debugging-in-wordpress/

### If you have customized a plugin or theme from the depository

8. When I click on auto-update will it replace any customization I have done on the plugin?

Yes. If you’ve edited the core files of a plugin you don’t maintain yourself, when it updates this will potentially replace any customizations made to the plugin you’ve edited. It is better to not edit plugin files directly without disconnecting them from their original source.

If you have fixed bugs or added features to a plugin, you could send these suggestions to the original author and ask them if they would like to push them to the main plugin repository to benefit others. These changes would then be reflected when you update the plugin on your site.

9. I have altered a theme to meet my website’s needs and changed the CSS, how do I stop the auto-update from losing my changes? 

Theme auto-updates are disabled by default. Administrators and site owners will need to enable this feature to receive automatic theme updates.

10. How do I avoid auto updating a theme I have customized for my site, for example, changed the CSS files, made a change in the JavaScript files or any other customization? 

If you’ve edited the core files of a theme you do not maintain yourself, then when it updates it will potentially replace any customizations made to the theme you’ve edited. 

You need to make sure you do not opt into auto-updates for the theme in question. This will prevent the auto-updates from happening. But better still use a child theme wherever possible. 

More information on how to set up a child theme
https://developer.wordpress.org/themes/advanced-topics/child-themes/

### Custom plugins and themes

11. Will clients get an auto-update message relating to custom plugins?

If the plugin hooks into the WordPress Updater, then the client will have the ability to turn custom updates on or off. If the plugin does not hook into the WordPress Updater, then nothing will display in the “Automatic Updates” column in the WordPress Dashboard. 

The link to the updater
https://make.wordpress.org/core/2020/07/30/recommended-usage-of-the-updates-api-to-support-the-auto-updates-ui-for-plugins-and-themes-in-wordpress-5-5/

12. I have a custom plugin added to my client’s WordPress website which is not going to need updating? 

Only plugins that hook into the WordPress updater will leverage the new auto-update feature. Custom built and installed plugins that do not hook in the WordPress updater will have nothing displayed in the auto-updates column for plugins. 

[Images](https://drive.google.com/file/d/1Yh-vlZpv6EWXyog0JcDTR4nbmQCkT3bt/view?usp=sharing)

## SECTION 2. IMAGE EDITOR

## SECTION 3. Block Directory Repository

## SECTION 4. Block Patterns
 
## SECTION 5. Gutenberg Update

## SECTION 6. Lazy-loading

## SECTION 7. XML Sitemaps

## SECTION 8. jQuery


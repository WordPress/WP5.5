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


## SECTION 2. Image editor

* [Devnotes link](https://make.wordpress.org/core/2020/06/24/whats-new-in-gutenberg-24-june/)
* [Field notes link](https://make.wordpress.org/core/2020/07/20/editing-images-in-the-block-editor/)

1. When a content editor is working with a post or a page and is making several changes in image size, would they be saved several times on a server or will each version replace earlier ones?

No, the ‘soft’ resizing of images still uses the originally uploaded image. It only sets the image size in the HTML img tag.

New images are created, and are visible in the Media Library, when a user edits an image, as in crops or rotates it.

2. Is this the same functionality we currently have within the media library?

No, this is new functionality only available in the block editor. The plan is to replace the old image editor, as found in the Media Library, with the new one.

This replaces the functionality in the current media library by adding a new API endpoint, named `https://sample.com/wp/v2/media/${ id }/edit`, this has been changed from `https://sample.com/__experimental//image-editor/(?P<media_id>[\d]+)`, which was the experimental launch of this feature, if you built any plugins using the experimental API endpoint you will now need to update it.  

There is a one-click external upload feature, within the normal block editor as seen in this GIF. 
https://make.wordpress.org/core/files/2020/07/uploada.gif

3. Does this affect the creation of custom image blocks?

The only effect from the update on the creation of custom image blocks is a new endpoint which to use.
```
/wp/v2/media/<id>/edit
```
This endpoint needs to be updated from the experimental feature that was originally deployed. 

4. Is the functionality packaged in some way that we can reuse and pull it into custom blocks for the repository?

Yes this is now included in a stable endpoint. You can read more about the feature release: https://make.wordpress.org/core/2020/07/08/whats-new-in-gutenberg-8-july/ 

5. How is this feature disabled? 
There isn’t a built in way to disable the new drag and [drop feature](https://github.com/WordPress/gutenberg/pull/23565). This feature and the other changes in the image editor in WordPress 5.5 are simply stabilizations of the API removing it from experimental status. 


## SECTION 3. Block Directory Repository

1. Where can I find more information on the Block Directory and Gutenberg updates in the 5.5 release for developers?

* [Dev Notes](https://make.wordpress.org/plugins/2020/07/11/you-can-now-add-your-own-plugins-to-the-block-directory/)
* [Field notes](https://make.wordpress.org/plugins/2020/07/22/proposed-block-directory-guidelines/)
* [Index for Gutenberg Development:](https://make.wordpress.org/core/handbook/references/keeping-up-with-gutenberg-index/)
* [Accessibility improvements in 5.5 for the core editor](https://make.wordpress.org/core/2020/08/06/wordpress-5-5-core-editor-accessibility-improvements/)
* [WordPress 5.5 Field Guide](https://make.wordpress.org/core/2020/07/30/wordpress-5-5-field-guide/)

2. Who can install blocks using the new Block Directory?

The block directory is a subset of the plugin directory. Only those users with permissions to add plugins (that is, site administrators) can add new blocks directly from the block directory. These blocks can be installed within the block editor itself. 

If a site administrator is editing a post or page, clicks on the ‘Add Block’ button, and searches for a block that is not installed, but available from the block directory, the block editor will give a prompt to install the block. For any other user type (editor/author), the following message is displayed “No blocks found in your library. Please contact your site administrator to install new blocks.”
If a user has administrative privileges, they will be able to add any blocks from the block directory, and then use these on any posts or page. 

This follows the same process as installing plugins. 

3. Will the block directory pull in blocks from all free plugins in the repository?

The block directory only includes blocks specifically from the WordPress.org plugin directory, which can be found under the blocks category. https://wordpress.org/plugins/browse/block/ 

For context, this category lists block plugins, which are a specific subset of plugins in the directory that only contains blocks for the block editor with no specific additional functionality. The directory will not show blocks from other block enabled plugins or themes.

To request a block addition to the directory, developers can submit blocks by following the process for block submission. Read about the block submission process.
https://make.wordpress.org/plugins/2020/07/11/you-can-now-add-your-own-plugins-to-the-block-directory/

4. Will the block directory download the plugin in the background?

Yes. The block plugin will automatically be downloaded for you.   

5. Is it possible to disable the block directory?

At the moment it is not possible to disable the block directory from the admin interface/ WordPress dashboard. It is however possible to disable the block directory via a hook.

More on this using a hook to disable the block directory can be found on GitHub
https://github.com/WordPress/gutenberg/issues/23961

6. How is a block plugin different from a regular plugin?

A block plugin is a specific type of WordPress plugin that only adds a single block to your site whereas typically a plugin would offer more robust functionality.

7. Where can I find block plugins?

With the Block Directory being added as a new feature to WordPress 5.5, you can find block plugins by using the Inserter to automatically search for available block plugins to install. You can also review the currently available block plugins at this link: https://wordpress.org/plugins/browse/block/

8. Can I find individual block plugins in a separate admin plugin page?
Block plugins are a subset of regular plugins. Any installed block plugin will be listed in the [Plugins List](https://wordpress.org/plugins/browse/block/) page alongside other WordPress plugins.


## SECTION 4. Block Patterns

1. What is the difference between a block pattern and a standard block?

Patterns are curated collections of blocks, often organized around a specific section or purpose. You don’t have to add each block within a pattern individually, but can use the patterns that are available in the built-in Block Library. To share an analogy, getting blocks is like getting wood and nails whereas getting block patterns is like getting a house or picnic table ready to go.

2. What is the difference between a block pattern and a reusable block?

Block patterns come pre-built based on common use cases identified on the web. They are included in the WordPress 5.5 release. 

Reusable blocks are ‘synchronized’ together, while block patterns are disconnected from each other. 

On the other hand, reusable blocks are user generated and heavily customizable based on what a user might want to add. Both features build on blocks as the smallest interaction unit. They should make it easier for people to quickly customize their posts and pages.

3. Are block patterns reusable?

A block pattern is designed to be used repeatedly. You can add as many as you would like to posts or pages.

4. Where can I get more block patterns?

Right now, only a selection of block patterns are being added to WordPress. If you would like more choices, you can explore plugins which have their own block pattern library. 

5. How can I switch block patterns off? | How to disable block patterns?

If your site don’t need block patterns, you can remove support of them in your theme:
```
remove_theme_support( 'core-block-patterns' );
```
6. Will theme authors be able to build their own combinations of blocks with custom styles?

Yes! This can be done using the register_block_pattern function. Further, while WordPress comes with a number of block patterns built-in, theme authors might also want to opt-out of the bundled patterns and provide their own set. To learn more about how to build your own block patterns or opt out of the default bundled patterns, please review this Dev Note on Block Patterns in 5.5.

7. Will developers need to use JavaScript to build these patterns?

https://github.com/WordPress/gutenberg/issues/17335

No! Block patterns can be created without JavaScript using the new register_block_pattern_category() function. To learn more, you can review the [documentation](https://developer.wordpress.org/block-editor/developers/block-api/block-patterns/) for this new function and check out posts from people in the community who created their own patterns ([Rich Tabor’s post](https://richtabor.com/build-block-patterns/), [Mel Choyce-Dwan’s post](https://melchoyce.design/2020/03/30/creating-a-simple-block-pattern-plugin-for-the-gutenberg-editor/)).
 
## SECTION 5. Gutenberg Update

1. Full site editing is an exciting new feature. How does the 5.5 release move us towards this?

The 5.5 release has two main areas of improvement that relate to the Full Site Editing focus: the Site Editor and the Navigation screen and Navigation block. 

Full Site Editing is not ready to be merged into core and remains an experimental feature that site administrators need to opt into with the Gutenberg plugin. Work on these areas helps set the groundwork for future functionality. 

More details about this work can be found under the heading ‘Experiments’ in this Gutenberg post. https://make.wordpress.org/core/2020/07/08/whats-new-in-gutenberg-8-july/ 

2. Will blocks be accessible within the website’s header and footer?

Blocks will only be accessible within the site header and footer if you are using a block based theme and the Full Site Editing experiment is enabled through the Gutenberg plugin. For more context, if you have block templates in a theme, they won’t be used until the Full Site Editing experiment is enabled. For now, developers are able to create block based themes including theme template files that are block enabled. 
Will there be documentation released for theme developers so we can react accordingly?

Yes, there is a WordPress tutorial on how to create a block based theme — https://developer.wordpress.org/block-editor/tutorials/block-based-themes/— . 

The original GitHub documentation on what a block is based on the readme found in github whioch details the structure layout and suggest functionality of a block based theme — https://github.com/WordPress/gutenberg/blob/master/docs/designers-developers/developers/themes/block-based-themes.md 

3. What is the difference between a block pattern and a reusable block?

Reusable blocks are meant to co-exist with regular blocks as a way for the user to make snippets of content that are globally synchronised. This is helpful if you find yourself repeatedly adding the same content to the same block or group of blocks. For example, if you’re writing a series of posts, you can use a reusable block to link to all posts in the series with each new post you share. Generally speaking, they are primarily user content and can be thought of as custom user blocks. 

Block patterns offer an entirely different approach both in behaviour and presentation to reusable blocks. Block patterns are saved locally upon insertion and don’t exist globally. They are just blocks the user can insert with starter content that is meant to be customized and updated by the user. 

4. Are updates to widgets and menus in WordPress 5.5 release? 

No. These features are related to the Full Site editing project and aren't available in 5.5.

## SECTION 6. Lazy-loading

1. Where will I find additional information on Lazy loading in WordPress for developers?

* [Dev Notes on lazy-loading](https://make.wordpress.org/core/2020/07/14/lazy-loading-images-in-5-5/)
* [Field Notes on lazy-loading relating to Release 5.5](https://make.wordpress.org/core/2020/07/14/lazy-loading-images-in-5-5/)
* [Loading images in WordPress core](https://make.wordpress.org/core/2020/01/29/lazy-loading-images-in-wordpress-core/)
* [Lazy-loading update](https://make.wordpress.org/core/2020/02/25/lazy-loading-update/)

2. How is lazy-loading implemented in WordPress 5.5?

The new lazy-loading technique will enable better performance and UX out of the box for the majority of users, without any additional work from developers, site owners and content editors. This feature is a new HTML standard and browsers which have no support for this feature currently,  will degrade gracefully back to the old standard.

Developers have the option to turn this feature off or customise it as usual implementing their own approach. For example, the attribute ‘loading’ with value ‘eager’ moves an image up to the top of the queue and means pre-fetching. Wisely used this can provide better experience for users and allows theme and plugins creators to be more flexible. 

WordPress 5.5 has implemented native lazy-loading with loading attribute lazy applied to all types of images in direct accordance with the HTML standard. Content, excerpt and widgets are filtered, users’ avatars and attachment images have this new attribute in the building process, including custom logo. 

This technique can be switched off for a particular type of context or completely by a new filter ‘wp_lazy_loading_enabled’.

Lazy loading doesn't apply to pixels in in-build code or images in CSS. CSS and JS use async attributes equal to lazy-loading, but in this case there are restrictions and downsides.  

3. Do I still need a lazy-loading plugin?

If the behavior of native lazy-loading in browsers doesn’t fit your purposes, you can continue to use plugins which implement lazy-loading through a different approach. 

Popular lazy-loading plugins replace images with placeholders and use scripts to reveal images as users scroll through the page. This implementation can have a negative impact on image SEO optimization. Google search declares support for such techniques, but still many developers do not rely on browser rendering to avoid damaging SEO. This is why in decoupled and headless WordPress, there is still a need for server rendering. There are also other popular search engines apart from Google, like Bing, DuckDuckGo and some which are more popular in different countries.

4. What is lazy-loading? | How does lazy-loading work?
Lazy-loading is a technique which allows images  to be loaded below the viewport and helps to make page response to user’s interactions quicker and enables faster initial load time. 

The lazy loading attribute as per the [whatwg standards](https://html.spec.whatwg.org/multipage/embedded-content.html#attr-img-loading) is defined as “The loading attribute is a [lazy loading attribute](https://html.spec.whatwg.org/multipage/urls-and-fetching.html#lazy-loading-attribute). Its purpose is to indicate the policy for loading images that are outside the viewport.” 

5. Are there any new functions and hooks for working with lazy loading in WordPress?

https://developer.wordpress.org/reference/functions/wp_filter_content_tags/
https://developer.wordpress.org/reference/functions/wp_lazy_loading_enabled/
https://developer.wordpress.org/reference/functions/wp_img_tag_add_loading_attr/
https://developer.wordpress.org/reference/hooks/wp_lazy_loading_enabled/
https://developer.wordpress.org/reference/hooks/wp_img_tag_add_loading_attr/

There are also a number of new functions related to images. You can find more information at the links below:
https://developer.wordpress.org/reference/functions/wp_img_tag_add_width_and_height_attr/
https://developer.wordpress.org/reference/hooks/wp_img_tag_add_width_and_height_attr/
https://developer.wordpress.org/reference/functions/wp_image_src_get_dimensions/
https://developer.wordpress.org/reference/hooks/get_custom_logo_image_attributes/

View a list of all new functions
https://developer.wordpress.org/reference/since/5.5.0/


## SECTION 7. XML Sitemaps

1. What happens to sites with existing sitemap plugins?

Many sites already have a plugin active that implements sitemaps. For most of them, that will no longer be necessary, as the feature in WordPress core suffices. However, there is no harm in keeping them. The core sitemaps feature was built in a robust and easily extensible way. If for some reason two sitemaps are exposed on a website (one by core, one by a plugin), this does not result in any negative consequences for the site’s discoverability.

2. What about image/video/news sitemaps?

These sitemap extensions were not considered a goal when the project was initially proposed. They will not be covered by this feature. In future versions of WordPress, filters and hooks may be added to enable plugins to add such functionality.

3. Are there any UI controls to exclude posts or pages from sitemaps?

No. User-facing changes were not part of the scope when the project was initially proposed. This is because simply omitting a given post from a sitemap is not a guarantee that it won’t get crawled or indexed by search engines. 

If you want to exclude posts from sitemaps, it would be better handled by dedicated plugins (that is, SEO plugins). These plugins implement a UI for relevant areas and can use the new filters to enforce their settings, for example, to only query content that is not flagged with a “noindex” option.

4. How can I disable sitemaps?

If you update the WordPress settings to discourage search engines from indexing your site, sitemaps will be disabled. Alternatively, use the wp_sitemaps_enabled filter, or use remove_action( 'init', 'wp_sitemaps_get_server' ) to disable initialization of any sitemap functionality.

The Yoast plugin version 14.5 from 8 July 2020 will disable the WordPress Core sitemaps as well as Jetpack version 8.7 from 7 July 2020. In the case where both plugins are used together and in both sitemaps are enabled, JetPack will disable Yoast sitemap.

5. How can I disable sitemaps for a certain object type or exclude a certain item?

Using the filters referred to above – check out the feature plugin page for examples.By default, no. Those are optional fields in the sitemaps protocol and not typically consumed by search engines. Developers can still add those fields if they want to using the filters referred to above.
More information on sitemaps in WordPress core.
https://wordpress.org/plugins/core-sitemaps/

lastmod in particular has not been implemented due to the added complexity of calculating the last modified dates for all object types and sitemaps with reasonable performance. For a common website with less frequent updates, lastmod does not offer additional benefits. For sites that are updated very frequently and want to use lastmod, it is recommended to use a plugin to add this functionality.

6. Are there any privacy implications of listing users in sitemaps?

The sitemaps only surface the site’s author archives, and do not include any information that is not already publicly available on a site.

Plugin developers can add custom content types or make changes to the privacy settings of default content types. These need to be done within the plugins.

Custom post types will appear on sitemap by default even if a post type is registered with parameter 'exclude_from_search' equal true.
Filter 'wp_sitemaps_post_types' can be used to exclude certain post types from the sitemap.

7. Are there any performance implications from adding this feature?

The addition of this feature does not impact regular website visitors, but only users who access the sitemap directly. Benchmarks during development of this feature showed that sitemap generation is generally very fast even for sites with thousands of posts. Thus, no additional caching for sitemaps has been put into place.

If you want to optimize the sitemap generation, for example by optimizing queries or even short-circuiting any database queries, use the filters mentioned above.

More about WordPress sitemaps https://make.wordpress.org/core/2020/07/22/new-xml-sitemaps-functionality-in-wordpress-5-5/


## SECTION 8. jQuery

1. What do I need to know and what I need to do?

The plan is for a three-step process across three WordPress releases from 5.5, 5.6 and 5.7. Details of how jQuery will be updated with WordPress
https://make.wordpress.org/core/2020/06/29/updating-jquery-version-shipped-with-wordpress/ 

This initial 5.5 release will only remove jQuery Migrate (which is one part of jQuery and not the core jQuery library) - the details are laid out in the plan above. 

We highly recommend you preemptively check your current sites using the plugin: https://wordpress.org/plugins/wp-jquery-update-test/  

This will help you detect any errors that may happen during the jQuery update planned for 5.6 and 5.7. 

Not loading jQuey Migrate by default could result in some broken sites. This will depend on the plugin and theme JavaScript code on the website. It is not expected that users will have issues, but there may be a number of plugins and themes which encounter some issues that will need resolving.

2. In the WordPress 5.5 update, a migration tool known as jquery-migrate is no longer enabled by default. This may lead to unexpected behaviors in some themes or plugins which are running run older code. 

https://wordpress.org/plugins/enable-jquery-migrate-helper/
This plugin serves as a temporary solution, enabling the migration script for your site to give your plugin and theme authors some more time to update,and test their code. To install the plugin: upload it to your plugins folder, usually wp-content/plugins/ activate the plugin on the plugin screen The plugin should handle the rest automatically for you. 

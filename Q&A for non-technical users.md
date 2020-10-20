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
### How will auto-updates benefit my site?

Your site will benefit in two ways:
Security: automatic updates will make your website less vulnerable to security breaches. Updates that fix vulnerabilities will be automatically installed. 
Convenience: You will no longer need to track available for updates, create back-ups and install them manually.
 
### Why do only some of the plugins show update notifications?

If you see some plugins with no update notifications or options, it may be a premium or custom plugin, or one that does not use the auto-update feature. Contact your website Administrator/Developer/Plugin Author (or wherever you purchased the plugin from) about how to keep it up to date and compatible with supported versions of PHP, jQuery and other WordPress Core features.  
 
### I have a third-party plugin(s), what does this mean for me?

Please be aware that some plugins may not auto-update, and some hosts may not allow auto-updates. Please be sure to 1) ask your host if they allow auto-updates 2) ask the plugin developer/author whether they are set up to send updates through the WP Admin. If either your host does not allow it, or your plugin is not developed to serve auto-updates this can prevent auto-updates regardless of whether you’ve updated to WP 5.5. 

If you do not have auto-update enabled for a plugin or for any reason your plugins cannot auto-update, you will need to follow the instructions provided by your host and plugin author/developer to manually update in order to ensure the best security for your site.

### Will auto-updates of themes and plugins mean my website will break?

Auto-updates are not switched on by default. You can enable auto-update on each plugin and theme.

If you or your site administrator has directly modified the theme rather than a child theme or via plugin code, then an auto-update can affect your website. There is a possibility that allowing an auto-update to your theme may have an effect on the design or even functionality changes which you had made directly to the theme.

Some steps that you can take are:
1. use a staging area to make a manual update before enabling the update 
2. make sure you have a recent backup before applying any updates
3. check if your theme has been built as a [child theme](https://developer.wordpress.org/themes/advanced-topics/child-themes/).

You can decide if and when to enable plugin and theme auto-updates, on a  theme-by-theme/ plugin-by-plugin basis. They are disabled by default - this is not affected by minor release versions, for example 5.5.1.

If something goes wrong with your site and you think it may be associated with an update, you or your site administrator should check for email notifications on which plugin or theme has been updated and their respective version number. This will help the Administrator manually rollback an update which they think may have contributed to a problem on your site. It is worth considering having automatic backups enabled for your website. This could be done by using a WordPress backup plugin.

If you run into issues, a good place to start debugging is the Site Health feature, which is available in your dashboard in WordPress release versions 5.1 and above. You can get an overview of your website characteristic and possible issues go to your site Dashboard » Tools » Site Health. 

### I don’t see any option to auto-update my plugins or themes

If you don’t see these options for any of the plugins on your site, your website administrator/developer may have switched them off so other users are not able to enable or disable anything by mistake. Make sure you have the correct user access permissions in order to use this functionality. 

As a WordPress site owner or manager, you can approach your plugin or theme author to incorporate the new Auto-Update feature.

### What do I do if my host updates to the latest WordPress your host is updating to the latest WordPress releases automatically?

If you have your plugins and theme auto-update enabled, your site will be more secure. Otherwise, WordPress will be updated and plugins and a theme will possibly experience compatibility problems. 

Note that WordPress does not auto-update between major updates and only minor updates are applied automatically. However, hosting companies may opt to make major updates as part of their automatic updating process. In this case check with your hosting company that you will receive notification when these updates happen so you can check your site’s operation.

In rare cases automatic updates between major versions may cause compatibility problems especially if you have custom plugins and themes which need special attention from their developers. Some premium plugins and themes may also need to be updated manually. This is another reason to have regular backups of your site, particularly before you update the WordPress version, plugins or themes.  

### I have a few sites and am getting a lot of emails about updates. How can I turn email notifications off?

To disable the default notification email sent by a site after an automatic theme and/or plugin update, your Developer/Site Admin can use two filters, with instructions here: https://make.wordpress.org/core/2020/07/30/controlling-plugin-and-theme-auto-update-email-notifications-and-site-health-infos-in-wp-5-5/  
If you wish to disable them yourself, you can search the WordPress.org directory for a plugin that disables theme and plugin auto-update emails.

###How to disable auto-updates in WordPress?

Auto-updates are disabled by default. But some plugin or theme authors can make auto update of their plugins mandatory and in this case you will not be able to switch it off even if you have full administrative rights.

Additional information:
https://wordpress.org/support/article/updating-wordpress/
https://wordpress.org/support/article/debugging-in-wordpress/



## SECTION 2. Image editor
### How can I zoom an image in Block Editor?
You can achieve it by using the zoom tool in the Image block.
Below are the steps to zoom an image:
* Add an image to the image block.
* Select the crop tool from the toolbar. The crop tool will be extended with the new toolbar.
* Select the zoom tool. It will display the slider tool with an aspect.
* Use the slider to zoom in/out the image.
* Click Apply to make the change to the image.
* Click Cancel to discard the change.

### How can I rotate an image in the Block editor?
You can rotate the image using the Image Block.
Below are steps to rotate the image:
* Add an image to the Image block.
* Select the crop tool from the toolbar. Crop tool will be extended with the new toolbar.
* Select the rotate tool. It will rotate the image in the editor itself.
* Rotate the image.
* Click Apply to make the change to the image.
* Click Cancel to discard the change.

### How can I crop an image in Block Editor?
You can crop the image using the crop tool of the Image block.
Below are steps to crop the image:
* Add an image to the Image block.
* Select the crop tool from the toolbar. Crop tool will be extended with the new toolbar.
* Select the aspect tool. It will list aspect ratio in a dropdown box. Aspect ratio can be set as per original, square, landscape and portrait of the image. 
* Select aspect ratio as per your requirement. 
* Move the image in the select aspect ratio to crop it.
* Click Apply to make the change to the image.
* Click Cancel to discard the change.

### Can I upload external images in the Image block?
You can upload any external image directly from the image block. 
Below are steps to upload external image:
* Add the Image Block. There are three options to add the image. 
* Click the “Insert from URL” option. There is a prompt of a text box for pasting the image link address.
* Copy the image link from external resources.
* Paste the image link in the upload image text box.
* The  image block will display the image from the external resources.
* Click on upload external image icon in the toolbar. It will upload the image into the media library.

### What will happen if I change an image several times?

Each time you edit an image and then move out of the image editor, the image is saved in the Media library separately. This can increase the size of your site folder on a server.  If you have limited space, please check directly with your Hosting provider on how to handle this.

## SECTION 3. Block Directory Repository

### How does the new block directory work?
With the new block directory, if you need to add a block to your page and you can’t find it on the list of blocks, you can use the search feature to discover, install and insert third-party blocks to your page.

When editing a post or page, on the top right corner you will see a plus ‘+’ sign that says “Add Block” when you hover over it. Click on it and you will see a search bar that says “search for a block”. You can enter the name of the block you’re looking for, or simply a keyword, just like you do when searching for regular plugins. If you see the block you want, just click on ‘Add Block’. If you get an error message such as “Error registering block. Try reloading the page.”, click on the ‘reload’ button which will load the page again, and you should be able to access your block plugin immediately.

### What is the difference between regular plugins and a block plugin?
Block plugins are small pieces of code - mostly JavaScript-based that outputs some HTML - that provide a block. They are searchable and installable from within the Gutenberg editor itself.
Regular plugins can add new features and significantly extend functionality, and you search for and install them from the Plugins menu. Block plugins impact a site at the page level while regular plugins mostly impact a site at the architecture and functionality level.

### There is a block I want to install, but I get a message saying “No blocks found in your library”.
If you don’t have an Administrator role in your WordPress site, you don’t have permission to add plugins, nor can you add new blocks directly from the block directory. You will need to ask your site administrator to install any new blocks.

### Where can I see and manage the block plugins used on my site?
They will appear in the Plugins list page along with your regular plugins, and you will be able to activate or delete them from that page.

### Is this going to mean more work or things to learn for users?
Blocks make creating and editing posts and pages easier for users. You can safely and seamlessly install block plugins without having to leave the Editor, instead of going through the process of saving what you’re working on and then going over to the Plugins menu. Just search for the block, add it, and continue with your work. 

## SECTION 4. Block Patterns
 
### What is a Block Pattern?
A Block Pattern is one or several blocks that are organized and stylized. If a pattern contains several blocks you can remove them or move them around separately. Styling abilities are determined by the functionality of The Block Editor and your current theme.

### What is the difference between a block pattern and a block?
Patterns are curated collections of blocks, often organized around a specific section or purpose. You don’t have to add each block within a pattern individually but can use the patterns that are available in the built-in Block Library. To share an analogy, getting blocks is like getting wood and nails whereas getting block patterns is like getting a house or picnic table ready to go.

### What is the difference between a block pattern and a reusable block?
Block patterns come pre-built based on common use cases on the web and are a part of WordPress with the 5.5 release. Block patterns can’t be created by users and saved. On the other hand, reusable blocks are user-generated and heavily customizable based on what a user might want to add. Both features build on blocks as the smallest interaction unit and should make it easier for people to quickly customize their posts and pages.

### Are block patterns reusable?
They’re not “reusable” as in Reusable Blocks, but you can add as many of the same pattern to as many posts or pages that you would like.

### Where can I get more block patterns?
Right now, only a selection of block patterns is being added to WordPress. If you would like more, you can explore plugins that have their own block pattern library.

### How is a block plugin different from a regular plugin?
A block plugin is a specific type of WordPress plugin that only adds a single block to your site whereas typically a plugin offers more robust functionality that impacts the entire website and not just a particular block.

### Where can I find block plugins?
With the Block Directory being added as a new feature to WordPress 5.5, you can find block plugins by using the Inserter to automatically search for available block plugins to install. Separately, you can also review the currently available block plugins on the page ‘Plugins categorized as block patterns. https://wordpress.org/plugins/browse/block/

### What will happen to a block pattern on my site if I switch themes?
If you change themes, the block patterns that were inserted into your post(s) will remain intact.

### What if a block pattern that I’m using is changed?
It is possible that a Block Pattern you’ve used on your site is changed or even removed in the future. This will not impact your site because once you’ve added a Block Pattern to your site, it is not linked to the original pattern and any changes will not affect your site’s posts or pages.



## SECTION 5: Gutenberg Update
### Why should I use the block editor?
The Block editor can help you produce nice layouts for your content with many in-built block choices and the new block patterns. With the new Block Repository you can also add new blocks into your block editor.

### I still use the classic editor, will this new update affect it?
No, the classic editor plugin will be maintained until 2022. In the Writing Settings of your site you can decide if you allow to choose which editor to use for each page or post. Alternatively, you can use the new Block Editor and use the Classic Block: https://wordpress.org/support/article/classic-block/

### Do I still need a third-party page builder?
Whether  you choose to use a page builder or not is entirely up to you as the end user, the potential compatibility of the page builder with these new Gutenberg updates is entirely dependent on the third party that develops your page builder. If you do run into issues we recommend you reach out directly to them we are sure they’d be happy to help you. 

### What’s the block pattern for?
The block patterns are ready-to-use blocks that you can add to your page. It can be a button, header, or any commonly used block. More patterns will be added with time. To understand the difference between blocks, patterns and layouts, visit: https://make.wordpress.org/design/2019/11/14/blocks-patterns-and-layouts/

### Can I use my page builder and the new block editor together?
It depends on which page builder you are using or want to use. We recommend you check on the documentation for the page builder you use.

### Will I still need the Gutenberg plugin?
You do not need to use the Gutenberg plugin in order to use the block editor. However if you do use the plugin, you will have access to newer features that are under development, and not yet included in the WordPress core.




## SECTION 6. Lazy-loading

### What is lazy loading?
Traditionally when the browser is loading a page: 

1. It requests all images (and additional files) at once, loading the entire page for the visitor in one go, whether or not the visitor has even gotten to scroll down the page yet. 
2. It does not allow any interactions, such as the use of buttons, until all these files have been loaded on a page.

Lazy loading solves these problems by loading a page 'on-demand', loading only the images  of a page that are required by the visitor at that moment. When the visitor scrolls down to view more content, only then will the images associated with that section of the page load. This provides a better user experience for your site visitors and improves your site’s performance.

1. Images with the loading attribute ‘lazy’ are loaded if they are in the viewport (the visible part of the webpage) or close to it. The definitions of this closeness is different across browsers, Chrome is more eager to load images to get user better visible performance, Firefox is more concerned about saving traffic and is loading right before they are about to enter viewport.

2. ‘Lazy’ images do not block interaction with the page even if they are right in a viewport and this allows users and site owners to expect better performance and UX.

Native lazy loading implemented in WordPress 5.5 uses the browser's native ability to delay loading of images until they are needed. This technique became a web standard in February 2020 and since then has been getting more and more support from browsers and now about 70% of browsers (currently in usage) have it already by default and in about 10% of the remaining this can be enabled manually in the browser settings.  

### How does lazy loading work in WordPress 5.5?
In WordPress 5.5 lazy loading is enabled by default for all images. An attribute is added to all images on the backend of WordPress automagically! 
This will not be applied though to images that are hard coded in the theme files or included through third party scripts such as tracking pixels. 

To be sure that the lazy loading is working correctly, if you are using Classic editor and correcting HTML code manually, do not remove width, height and class attributes of images which are default attributes of images added by WordPress. 

### Do I still need a lazy loading plugin?
You shouldn’t need a separate plugin to enable lazy loading in WordPress anymore after you update to WordPress 5.5. 

### Do I need a developer to make lazy loading work in WordPress?
In WordPress 5.5 lazy loading of images is enabled by default and there is no need to do anything to get lazy loading to work. 

Please note, lazy loading won’t apply to images without a width / height attribute. 

### Does lazy loading have cons?
Native lazy loading implemented in WordPress is safe to use on all sites. This is a User Experience (UX)  improvement and browsers which don’t support this will not be affected. 

Native lazy loading implementation in WordPress 5.5 has no cons.

Currently about 70% of users’ browsers can lazy load images and because this will become a standard in the beginning of 2020 year, we can expect this number to rise. 

### How do I know if lazy loading is working?
You can use one of the popular web page test tools such as google PageSpeed or Lighthouse, it should indicate which images are being loaded lazily or not.
If you continue to see "defer offscreen images" or similar recommendations in Lighthouse or PageSpeed Insights even when lazy loading is enabled, contact your developer or check the [Support forums](https://wordpress.org/support/forums), where someone else may have had the same issue.


## SECTION 7. XML Sitemaps
### I don’t want this sitemap. How do I disable it? 
If you currently use an [SEO plugin](https://wordpress.org/plugins/search/SEO/) or a [sitemap plugin](https://wordpress.org/plugins/search/sitemap/) that generates your sitemaps, the core sitemap will most likely be disabled by default and you don’t need to do anything, just make sure you have the latest version of the plugin. You can always double check this with your plugin’s support team. 

If you don’t currently use a plugin but still want the core sitemap disabled, you can change the site visibility settings in your WordPress Admin to discourage search engines from indexing your site. 

If you don’t make the changes to your site, ask your Developer or the person who makes your site changes to disable it using a filter. They can see the Developer documentation for instructions. 

### There are some posts on my site I don’t want to be visible
If you want to exclude certains posts or pages from your sitemap, it’s best you rely on a dedicated plugin to do so. Keep in mind that the sitemaps only surface content that is already publicly available in your site.

### I already have a sitemap generated through a plugin, what do I do?
If you are using a sitemap plugin, you may no longer need it as your sitemap needs may already be covered by the core sitemap. If you currently use an [SEO plugin](https://wordpress.org/plugins/search/SEO/) or a [sitemap plugin](https://wordpress.org/plugins/search/sitemap/) that generates your sitemap, the core sitemap will most likely be disabled by default so nothing will change for you and you don’t need to worry about conflicts, just make sure you’ve updated to the latest version of your plugin. You can always double check this with your plugin’s support team. 

### How does my site benefit from a sitemap?
An XML sitemap lists the URLs on your site that you want to be publicly available. It helps search engines like Google and Bing crawl your website thoroughly and understand what URLs are important, by providing them with a map of your site’s content. 

### What to do if I have indexed sitemap already?
If you currently use an [SEO plugin](https://wordpress.org/plugins/search/SEO/) or a [sitemap plugin](https://wordpress.org/plugins/search/sitemap/) that generates a sitemap or a sitemap index, the core sitemap will most likely be disabled by default and you don’t need to do anything, just make sure you have the latest version of the plugin. In cases where a sitemap or SEO plugin does not disable this new sitemap, you may have the new sitemap indexed by search engines simultaneously with the others.

Websites can have several sitemaps and they can be indexed simultaneously. In cases where you end up with a sitemap additional to the one(s) you already have, there is little harm in them co-existing, but you whichever you submit to Google Search Console will be prioritised over the one indicated in the robots.txt file.



## SECTION 8. jQuery
After updating to WordPress 5.5 I have issues regarding scripts and unexpected behavior of elements on my site. What do I need to do?

### I updated to WordPress 5.5 and now something went wrong with scripts on my site.
### I updated to WordPress 5.5 and now I cannot save anything in the admin.
### I updated to WordPress 5.5 and sliders on my pages don’t work.

The WordPress.org core team has put together a plugin to re-enable the first file that was removed in 5.5 to help mitigate these issues and give the plugin and theme authors time to perform the needed updates. 
This plugin is called “enable jQuery migrate helper” and can be found at: 
https://wordpress.org/plugins/enable-jquery-migrate-helper/

After installing this plugin, many people have found that a lot of the errors they have developed during the 5.5 update have disappeared.

### Why is WordPress updating jQuery? 
WordPress is planning during the two releases 5.5 and 5.6 to phase out an old, unsupported version of the popular front-end JavaScript library “jQuery”. During this transition period, Plugin and theme authors are obliged to take it upon themselves to update their own themes / plugins to the latest version of jQuery, this may cause some issues.

 
### How do I know if I have problems with scripts on my site after an update to WordPress 5.5?
If something behaves in a different way to what you are expecting or how it behaved prior to the update. For example, you can not update a post, the slider doesn't work or buttons don’t react, all these point towards potential possible problems with scripts.

The best way to know if your site has any developed any errors is to thoroughly check all actions on the site, such as but not limited to: 
* submitting forms 
* purchasing products 
* logging-in 
* testing sliders / carousel  

Please note that not all errors on your site may have developed or can be solved by enabling the jQuery Migrate Helper plugin. 

### I want to update my site to WordPress 5.5. How can I be sure that plugins and theme on my site are compatible with the working version of the script library jQuery? 
We highly recommend you preemptively check your current sites using the jQuery update test plugin: https://wordpress.org/plugins/wp-jquery-update-test/  

To test your site ready for jQuery:
- Please make sure you first install the jQuery Migrate plugin: https://wordpress.org/plugins/enable-jquery-migrate-helper/
- Then install the jQuery update text plugin: https://wordpress.org/plugins/wp-jquery-update-test/ 
- Now you need to configure the plugin by going to Plugins -> Test jQuery Updates 
- In the Test jQuery Updates plugin, set the options as below:
  - jQuery version: Default (This will be the default jQuery version used in the WordPress Core)
  - jQuery Migrate: Disable (Keep it disabled for WordPress 5.5.)
  - jQuery UI version: Default
  
More information on how to do this can be found on the plugin page: 
https://wordpress.org/plugins/wp-jquery-update-test/



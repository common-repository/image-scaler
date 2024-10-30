=== ImageScaler ===
Contributors: PaulButler, DavidKarlsson
Tags: images, image
Requires at least: 2.0.2
Tested up to: 2.3
Stable tag: trunk

Resamples images after they are resized in the post editor. This makes them look better and download faster.

== Description ==

ImageScaler resamples image files that have been resized in the post editor.

When images are resized in the WordPress post editor, the images themselves stay the same and the browser 
is instructed to resize the images after downloading them. This wastes bandwidth, and results in ugly
looking resized images. To eliminate this problem, the ImageScaler plugin checks for the image sizes in
each post and resizes the images if required. The original image is not modified, so it can still be
used in other posts at full size.

By default, an extra attribute is added to some of the image tags in each post. The attribute is non-standard,
so it may cause (x)html validation to fail. If you require valid (x)html, the plugin has an option that
strips the non-standard output from the post before it is sent to the browser.

This is the first version of ImageScaler. Please contact me at `paulgb at gmail dot com` if you find a bug
or have unexpected results.

== Changelog ==

1.0 - October 4, 2007
(Big thanks to David Karlsson for writing this version)
- Added maximum height and width
- Added check for GD

1.1 - October 20, 2007
- Now works on remotly hosted images (mirrors remote images locally, even if they are not resized)
- Now works if the WordPress blug URL differs from the WordPress home directory (thanks Dominique)
- Tested with WordPress 2.3
- Aspect ratio is now always preserved, not just when a maximum is reached

== Installation ==

This plugin requires gd to modify the image files. Also, PHP must have write access to the wp-content/
directory. If you prefer, you can create the wp-content/imagescaler/ directory and give PHP write access
to that instead.

As long as you meet the requirements, installation is easy. Just upload `imagescaler.php` to the 
`/wp-content/plugins/` directory, and activate it through the Plugins tab in WordPress.

Once installed, every time a new post is created or any post is updated, the plugin will check all the
images in it and see if they need to be resized. Posts that were written before the plugin is insatalled
will not be changed unless they are updated.

If you require valid html, go to the options tab in the admin panel, and then go to the ImageScaler tab.
Check the box that says "Force strict xhtml" and click "Update Options".

If you decide to uninstall ImageScaler, the resized images (stored in /wp-content/imagescaler/) will
still be used, but images in new posts will not be resized.

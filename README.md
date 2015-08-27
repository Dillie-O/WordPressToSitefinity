#WordPressToSitefinity

This is not a standalone project. It must be placed inside of a Sitefinity 7.0 or later project and run from there.

##What's New
* Added CsQuery library (no need to download).
* Added result label to display when processing is finished.
* Added default e-mail to lookup default user with for blog imports.
* Removed tag / metadata processing (causes errors)
* Fixed image import process by handling images that link to larger versions of the image in WordPress.
* Updated summary field to use stripped down content from body if no summary is found (using HtmlAgilityPack).

##What it does

This tool imports blog posts from WordPress export files in to Telerik Sitefinity blogs.

**Current Functionality**

* Tags and Categories can be automatically created in Sitefinity and assigned to the posts
* Images found in post content are downloaded from their remote location, stored inside Sitefinity libraries, and included in the new blog post using [sfref]
* Import post comments.
* Import post thumbnail images.
* Import post full sized images (linked through href).

##Dependencies

* CSQuery - Included in repository.
* HtmlAgilityPack - Should be included in Sitefinity. If not, you can get it here.

##Please note

Currently, this if intended for developers already familiar with Telerik Sitefinity since it may require some modification depending on the exact scenario.

Suggestions and pull requests are totally welcome!

##How to hook everything up

###What to do first

All authors must already have accounts created in Sitefinity in order to properly map the posts to them. If you don't want this, create a single user and specify their e-mail address in the `_defaultAuthorEmail` field to have all blog posts mapped to them.

This version of the script does not parse any meta data, related content, etc. If you want to include that, you will need to create those resources in advance, uncomment the code in the script, (near line 166) and update it accordingly.

###Copying the source files

Merge the source files into your project.

##Running the import

_Make sure to do a backup of your project (including the database!) before attempting the import. Just in case, ya know. :)_

1. Navigate to ~/Migration/WPM.aspx to upload your WordPress XML dump and select the options you'd like.
2. Click 'Run'

# Error after update of easyapach
    Your PHP installation appears to be missing the MySQL extension which is required by WordPress.

Thi error happens when the extention mysqli is not installed.

The other reason for this is that there is a custom php.ini with wrong configurations.

In my case there was a php.ini in the root of the site with this line:

    extension_dir = ./

This was causing that the extesions were not found and not loaded.


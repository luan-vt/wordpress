## Overview
This is a Dockerfile/image to build a container for Wordpress with nginx, php-fpm, and necessary extensions. The container also has the ability to update templated files with variables passed to docker in order to update your code and settings.

If you have improvements or suggestions please open an issue or pull request on the GitHub project page.

### Environment
The following environment variables are also honored for configuring your WordPress instance:
    `-e WORDPRESS_DB_HOST=...`
    `-e WORDPRESS_DB_USER=...`
    `-e WORDPRESS_DB_PASSWORD=...`
    `-e WORDPRESS_DB_NAME=...`
    `-e WORDPRESS_TABLE_PREFIX=...`
    `-e WORDPRESS_AUTH_KEY=...`, `-e WORDPRESS_SECURE_AUTH_KEY=...`, `-e WORDPRESS_LOGGED_IN_KEY=...`, `-e WORDPRESS_NONCE_KEY=...`, `-e WORDPRESS_AUTH_SALT=...`, `-e WORDPRESS_SECURE_AUTH_SALT=...`, `-e WORDPRESS_LOGGED_IN_SALT=...`, `-e WORDPRESS_NONCE_SALT=...` (default to unique random SHA1s, but only if other environment variable configuration is provided)
    -e WORDPRESS_DEBUG=1 (defaults to disabled, non-empty value will enable WP_DEBUG in wp-config.php)
    -e WORDPRESS_CONFIG_EXTRA=... (defaults to nothing, non-empty value will be embedded verbatim inside wp-config.php -- especially useful for applying extra configuration values this image does not provide by default such as WP_ALLOW_MULTISITE; see docker-library/wordpress#142 for more details)

If the WORDPRESS_DB_NAME specified does not already exist on the given MySQL server, it will be created automatically upon startup of the wordpress container, provided that the WORDPRESS_DB_USER specified has the necessary permissions to create it.

### Versioning
| Docker Tag | Git Release | Nginx Version | PHP Version | Alpine Version |
|-----|-------|-----|--------|--------|
| latest | Master Branch |1.18.0 | 8.0.2 | 3.13.1 |


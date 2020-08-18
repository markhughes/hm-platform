<table width="100%">
	<tr>
		<td align="left" width="70">
			<strong>HM Platform</strong><br />
			Shared library for sites on the Human Made Platform.
		</td>
		<td align="right" width="20%">
			Version 1.4.3
		</td>
	</tr>
	<tr>
		<td>
			A <strong><a href="https://hmn.md/">Human Made</a></strong> project. Maintained by @markhughes.
		</td>
		<td align="center">
			<img src="https://hmn.md/content/themes/hmnmd/assets/images/hm-logo.svg" width="100" />
		</td>
	</tr>
</table>

## HM Platform

This is the HM (Human Made) Platform library that should be included on
all sites that are being hosted by Human Made. This includes some plugins that
are required for the hosting platform, however these _can_ be disabled if alternative
versions of plugins are installed.

See the [the wiki](https://github.com/markhughes/hm-platform/wiki) page for details on the
libraries that are included.

### Install Instructions

1. Add this repository to the content directory of the WordPress install, we recommend you add
it as a git submodule.
1. Require the `hm-platform/load.php` file from your `wp-config.php` before we include the
`wp-settings.php` file at end.

### Configuring Activated Modules

To optionally disable any of the platform modules, you can define the `global $hm_platform`
variable setting any of the following to true or false. The defaults are as shown:


```php
$defaults = array(
	's3-uploads'      => true,
	'aws-ses-wp-mail' => true,
	'tachyon'         => true,
	'cavalcade'       => true,
	'batcache'        => true,
	'mercator'        => false,
	'memcached'       => false,
	'redis-cache'     => false,
	'redis'           => false,
	'ludicrousdb'     => true,
	'xray'            => true,
	'elasticsearch'   => defined( 'ELASTICSEARCH_HOST' ),
	'healthcheck'     => true,
	'require-login'   => false,
);
```

### Search Engine Indexing

By default, hm-platform will force disable indexing by search engines on any non-production environment. If you wish to disable this feature, add the following to your config:

```php
define( 'HM_DISABLE_INDEXING', false );
```

This will fall back to whatever the `blog_public` option value is in the database.

## Testing Notes

### Table of Content
- [Introduction to PHP Unit Testing](#introduction-to-php-unit-testing)
- [Overview of PHP Testing](#overview-of-php-testing)

### Introduction to PHP Unit Testing

- Purpose: Get Conceptual understading of PHPUnit Testing using WP_PHPUnit for WordPress Plugin / Theme

#### Pre-Requisites

1. Knowledge of WordPress Development
2. Knowledge of writing basic PHPUnit Test
3. Using Composer & NPM

### PHPUnit Installation Guides (Stackoverflow) - Recommended
```
curl https://phar.phpunit.de/phpunit.phar -L -o phpunit.phar
chmod +x phpunit.phar
sudo mv phpunit.phar /usr/local/bin/phpunit
```

### PHPUnit Installation Guides (rtCamp LMS)

1. Core PHPUnit setup
    - Add a (development-time) dependency on phpunit/phpunit to project’s composer.json file 
    - `composer require --dev phpunit/phpunit`

2. Run PHPUnit tests 
    - Run PHPUnit tests by running the command from plugin root directory.
    -  `./vendor/bin/phpunit`

## WP-CLI Intro
- Powerful command-line tool for managing WordPress installations. 
- Allows developers to perform various administrative tasks without the need for a browser.

1. Installing using brew
```
brew install wp-cli
```

2. Verifying Installation
```
wp --info
```

3. Useful commands
```
// Update WordPress Core
wp core update
 
// Install a plugin
wp plugin install <plugin-slug>
 
// Activate a plugin
wp plugin activate <plugin-slug>
 
// Run unit tests
wp scaffold plugin-tests <plugin-slug>
```

### WP-PHPUnit Setup with WP-CLI

- Minimum Requirements:
    PHP
    MySQL Server
    WP CLI
    SVN

#### Step 1:
1. Open your terminal and go to your plugin/theme’s root directory

```
cd wordpress/wp-content/plugins/<your-plugin>/
```

2. Run the wp scaffold command:

```
wp scaffold plugin-tests <plugin-name>
```

This should create 2 directories and 1 file

bin: This contains the installing file.
tests: Contains a bootstrap file and a sample test case file.

phpunit.xml.dist file: Used to configure PHPUnit & create test suites

#### Step 2:
1. Run `bin/install-wp-tests.sh`

2. Provide the following arguments for it to run:

3. For bash shell:

```
bash ./bin/install-wp-tests.sh <db-name> <db-user> <db-pass> [db-host] [wp-version]
```

4. For zsh shell:
```
zsh ./bin/install-wp-tests.sh <db-name> <db-user> <db-pass> [db-host] [wp-version]
```

```
<db-name> - Name of the test database you created.
<db-user> - User of the database.
<db-pass> - Password of the Database user.
[db-host] - Host of the database (Usually localhost).
[wp-version] - WordPress version to download to run the tests.
```

This will create a test DB & create a new WP installation in /tmp

#### Step 3: Optional If Installed PHPUnit Globally
Install phpunit as project dependencies:
```
composer require --dev phpunit/phpunit
```

#### Step 4:
Install Yoast PHPUnit polyfills:
```
composer require --dev yoast/phpunit-polyfills:"^2.0"
```

#### Step 5:
Comment out the excluded test from the phpunit.xml.dist file.
```
<?xml version="1.0"?>
<phpunit
	bootstrap="tests/bootstrap.php"
	backupGlobals="false"
	colors="true"
	convertErrorsToExceptions="true"
	convertNoticesToExceptions="true"
	convertWarningsToExceptions="true"
	>
	<php>
		<env name="WP_TESTS_PHPUNIT_POLYFILLS_PATH" value="vendor/yoast/phpunit-polyfills" />
	</php>
	<testsuites>
		<testsuite name="testing">
			<directory prefix="test-" suffix=".php">./tests/</directory>
			<!-- <exclude>./tests/test-sample.php</exclude> -->
		</testsuite>
	</testsuites>
</phpunit>
```

#### Step 6: Run in plugin root:
```
./vendor/bin/phpunit 
# OR
phpunit
```

## Overview of PHP Testing

Testing in PHP is crucial for ensuring high-quality code and preventing the introduction of bugs with new features. It can be divided into three main categories:

1. **Unit Testing:** This involves testing individual components, such as functions or classes, in isolation. The goal is to ensure each unit of the software performs as expected.

2. **Integration Testing:** This type of testing focuses on verifying the interactions between different units or components of the application. It combines multiple units to test them together.

3. **End-to-End (E2E) Testing:** E2E testing examines the entire application flow from start to finish. It simulates real user scenarios to ensure the complete system functions correctly. This is also known as UI testing.

**Testing Tools**

- **PHPUnit:** A tool for unit testing in PHP.
- **Pest:** Offers a syntax similar to Jest, which is used in JavaScript.
- **Codeception:** Useful for E2E testing, especially with WordPress.
- **Cypress:** An effective tool for E2E testing, primarily in JavaScript environments.
- **Playwright:** A newer tool compatible with PHP and WordPress for E2E testing.
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


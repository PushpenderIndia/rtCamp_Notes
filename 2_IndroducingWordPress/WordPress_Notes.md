## Introducing WordPress

- Agenda
    - Basic Usage
    - Administration
    - Customization using Plugins & Themes
    - WordPress Editor (Block Editor)
    - Various Terminologies
    - MultiSites

### What is WordPress ?
- Free & Open Source CMS that powers more than 43% of the web
- Ability to create any type of website i.e. 
    - Blog
    - eCommerce
    - LMS
    - Social Networks
    - Membership sites

- Written in PHP & MySQL database is used
- Compatible with most web servers i.e. 
    - Apache Web Server
    - NGINX
    - Microsoft IIS.

### WordPress Multisites
- WP Multisites allows you to run multiple WordPress websites from single codebase
- Sharing same WP core, plugins & themes across the network
- Different techniques is used as per nature of project
    - **Installing WP in subdirectory**: Useful for adding a separate site or section with main domain
    - **Installing WP in subdomain**: Ideal for creating separate site for different services or brands within main domain
    - **Installing WP in Multisites**: Suitable for managing multiple sites with shared code, themes & plugins `but with separate content & data`

### Assignment for this Module
- Create a website using the Astra theme
- Create a website using the Food-mania Theme

### Installing WordPress & Creating Astra site
1. Open LocalWP & Create a new site using `+` sign using Preferred settings
2. Press Command + Space
3. Type `Keychain Acess` & Hit enter
4. Click on `Open Keychain Access` in the popup
5. Search the site name (e.g. astra) in search bar
6. Double click the SSL certificate
7. Click on `Trust` dropdown
8. Set the value of `When using this certificate` to `Always Trust`
9. Re-open the LocalWP

### Error: Port 80 is already in use
```
sudo lsof -i:80; sudo lsof -tnP -i:80 | xargs -n 1 ps -p
kill -9 <PID>
```

### How to Create Astra theme WordPress site
1. Once WordPress is installed, click on `WP Admin` from LocalWP
2. Click on `Appearance` > `Themes` > `Add New Theme` > Search `astra` 
3. Click on `Install` & then `Activate` this theme
4. Delete other default themes
5. Click on `Plugins` > `Add New Plugin` > Search `starter template`
6. Click on `Install` & then `Activate` this plugin

- Detailed Walkthrough: [YouTube Video Link](https://www.youtube.com/watch?v=gjLa-FT7JWg)

### Customizing WordPress Plugins
- In WordPress, themes are used to alter appearance of site
- Plugins are used to extend WordPress's functionality

1. Finding & Installing Plugins
```
Navigate to Plugins > Add New > Search for plugins
```
2. Checking Compatibility of New Plugins
```
Each plugin description includes a note that reads "Compatible with your version of WordPress” or “Untested with your version of WordPress.”

Click on "More Details" to see info about plugin's compatibility
```

3. Installing Plugins
```
There are 3 ways:
```

    1. **Automatic Plugin Installation**: 
        - Any plugin available in the WordPress Plugins Directory can be installed via the built-in plugin installer.
        - Navigate to `Plugins > Add New`
        - Use search bar for finding plugin
        - Click on `Install Now`
        - Once plugin is installed, click on `Activate`

    2. **Upload via WordPress Admin**: 
        -   You can easily add a new plugin by uploading a zip archive of the plugin from your local computer.
        - Navigate to `Plugins > Add New`
        - Click `Upload Plugin`
        - Select plugin zip file from local file system
        - Click on `Install Now`
        - Once plugin is installed, click on `Activate`

    3. **Manual Plugin Installation**: 
        -  In some cases, you may need to manually upload a plugin directly using an SFTP client.
        - Download plugin zip from [WordPress Plugin Directory](https://wordpress.org/plugins/) & unzip it locally
        - Transfer the extracted folder to `wp-content/plugins` directory of your WP via SFTP or remote file manager
        - From Plugins menu in Admin Screen, click `Activate` 

4. Updating Plugins
    - Manual Plugin Update from Dashboard
        ```
        WP Dashboard automatically notifies when plugin update is available
        ```
        - Click on `Dashboard -> Updates`
        - Scroll down to Plugin Section
        - Select checkbox & click `Update Plugins` button

    - Enable Automatic Plugin Update
        - Go to `Plugin -> Installed Plugins`
        - In the `Automatic Updates` column, there is button to `Enable auto-updates`

    - Disable Automatic Plugin Update
        - Go to `Plugin -> Installed Plugins`
        - In the `Automatic Updates` column, there will be a button to `Disable auto-updates`, if plugin was set to auto-updates

5. Uninstalling Plugins
    - Deactivate the plugin from `Plugins` section
    - Then you will see a option to `Delete` it

### Customizing WordPress Theme
1. Get New Theme
    - Click on `Appearence -> Themes -> Add New`
    - Either search for a free theme from Dashboard
    - Or you can upload a zip file 

2. Adding New Themes by using cPanel
    - Download theme in .zip format
    - In `cPanel File Manager`, navigate to themes folder i.e. `/wp-content/themes/`
    - Uploas & Unzip the theme file

3. Activating the Theme
    - Click on `Appearence -> Themes -> Click on Activate`
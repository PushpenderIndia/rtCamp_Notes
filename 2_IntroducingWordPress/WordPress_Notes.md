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

### WordPress Terminology

- **Back-end**: The back-end refers to the section of your website where you can log in and manage everything from your Dashboard.
- **Codex**: The official WordPress manual containing support articles, documentation, code snippets, and links to external resources.
- **Content Management System**: Software designed to manage the content on a website.
- **cPanel**: A web-based administration tool for managing your web hosting account.
- **Database**: Software used to store and manage data in an organized manner.
- **Default Theme**: The theme that comes pre-installed with a fresh WordPress installation. It also serves as a fallback theme if the current theme experiences issues.
- **DNS**: Refers to the Domain Name System, which maps domain names (like google.com) to their IP addresses.
- **DOM**: An interface that enables programmers to dynamically access HTML and XML on a web page.
- **Domain Name**: A system used to assign easy-to-remember names to website IP addresses.
- **Footer Area**: The horizontal section at the bottom of a website where widgets and copyright information are typically displayed.
- **Front-end**: The user-facing part of your website where visitors can view and interact with your content.
- **Gravatar**: A service that allows users to associate a global avatar (image or photo) with their email addresses.
- **Header Image**: A wide image that can be set to appear at the top of your website.
- **Hosting Provider**: A company that offers space on a web hosting server for a fee.
- **IDE**: An application that provides all the tools necessary for software development and testing.
- **Menu**: A collection of links to pages, categories, and social media profiles on your website, usually displayed in the navigation area.
- **Meta**: The meaning can vary in WordPress depending on its usage, but it’s typically used to refer to administrative data.
- **Multisite**: The ability to create a network of WordPress sites from a single WordPress installation.
- **Navigation**: A set of links on your website that assists site visitors in navigating through your content.
- **Nonce**: A one-time token generated by WordPress to protect your site against unexpected or duplicate requests, which could lead to permanent or unintended consequences.
- **Permalink**: A permanent link to content on your website, making it easy to share unique pages with others.
- **Sidebar**: A location on your website where you typically display elements like the search bar, recent and popular posts, and other important widgets. A website can have more than one sidebar.
- **Toolbar**: The small black bar just above your site that provides quick links to various parts of your website, usually visible only to logged-in users.
- **XML-RPC**: A remote procedure call (RPC) protocol that uses XML to encode its calls and HTTP as a transport mechanism.

### FSE (Full Site Editing) Introduction
- Introduced in WordPress 5.9
- Focuses on User Editability of Different site templates without making any changes in code
- Umbrella project name for various sub-projects within Gutenberg

```
Core Concepts of FSE are:
```
1. Site Editor
    - Used for building a site using blocks, layouts, templates, menus etc
    - Supported in Block Themes
    - Go to `Appearance > Editor` to open the Site Editor

2. Blocks
    - Individual & Customizable components of template or page
    - Can Build a page, post, template etc, by combining multiple blocks together

3. Templates
    - A list of block items collectively is known as a template
    - Can be used for page, post, archive, etc

4. Block themes
    - Themes which support blocks & can be edited with Site Editor are called block themes
    - Contains `theme.json` file that can be used to configure theme support & options

### Multisite / Network

- WordPress allows us to set up a Network of sites using same core files but with different login credentials & separate dashboards.

- Each site is independent of each other but can be managed from one place by Network Admin (aka Super Admin)

- Feature can be enabled by adding 1 line of code in `wp-config.php`

### Using Multisite WordPress Environment

1. Open LocalWP & Create a fresh site
2. In the third step of `Set up WordPress`, there is a option to enable MultiSite
3. From the dropdown `Is this a WordPress Multisite?` either select `Yes - Subdirectory` or `Yes - Subdomain`

4. Types of Multisite
    - Subdirectory Multisite - e.g. `myproject.local/site-1-name/`
    - Subdomain Multisite - e.g. `site-1-name.myporject.local`



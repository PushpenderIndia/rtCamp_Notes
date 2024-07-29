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



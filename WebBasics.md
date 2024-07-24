## Browser and Rendering Engines
### Steps of browser rendering:

1. **Parsing HTML**: The HTML code is parsed to build the Document Object Model (DOM), representing the content structure.
2. **Parsing CSS**: The CSS is parsed to create the CSS Object Model (CSSOM), defining the page's styling.
3. **Render Tree**: The DOM and CSSOM are combined to form the Render Tree, which includes how elements are displayed and styled.
4. **Layout Flow**: The browser calculates the layout, determining the size and position of elements based on the Render Tree.
5. **Painting**: The Render Tree is converted into pixels on the screen, with calculated values applied pixel-by-pixel.

## Web Servers

- User Flow
```
user ➞  browser ➞ internet ➞ web server ➞ application server (WordPress) ➞  php ➞ mysql
```

- Web Ports
Web servers most commonly listen on port 80 (unencrypted) or 443 (encrypted) on the server.

## WordPress and Emails
- WordPress out of the box sends emails using PHP’s mail function. 
- PHP in turn by default uses `Sendmail`.
- Email Flow
```
WordPress wp_mail() ➞ PHP mail() ➞ OS sendmail
```

- Email reliability can be improved by switching to `Postfix` 
- Which enables support for `SPF` and `DKIM` Protection.
- In `Production`, `AWS SES` is used. 
- There is a option to use `Gmail SMTP with WordPress`
- For `Development` environment, `LocalWP` is highly recommended because it has built-in `MailPit`
- `MailPit` captures the outgoing mails, shows them in its mailbox & dispose them

### Wordpress Email Redirects
- WordPress offers method to add an email account that continuously checks for new emails 
- Publishes everything sent to that email address.
- For processing incoming emails, we need to have a publicly reachable mailbox such as support@example.com 
- Then a program to “download” emails from this mailbox using something like IMAP or POP3.



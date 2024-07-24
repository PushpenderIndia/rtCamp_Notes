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

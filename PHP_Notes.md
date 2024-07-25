**PHP: Hypertext Preprocessor**

**Introduction:**
- PHP is a server-side scripting language designed for web development.
- Embedded within HTML to create dynamic web pages.

**Basic Syntax:**
- PHP code starts with `<?php` and ends with `?>`.
- Statements end with a semicolon `;`.
- Comments: Single-line `//` or `#`, Multi-line `/* */`.

**Variables:**
- Declared with `$` followed by the name (`$variable`).
- Case-sensitive.
- Types: Integer, Float, String, Boolean, Array, Object, NULL.
- No explicit type declaration; PHP is loosely typed.

**Data Types:**
- **Integer**: Whole numbers, e.g., `$num = 123;`
- **Float**: Decimal numbers, e.g., `$price = 10.99;`
- **String**: Text, e.g., `$text = "Hello, World!";`
- **Boolean**: `true` or `false`
- **Array**: Collection of values, e.g., `$array = array(1, 2, 3);`
- **Object**: Instance of a class.
- **NULL**: Represents a variable with no value.

**Operators:**
- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
- Comparison: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
- Logical: `&&`, `||`, `!`

**Control Structures:**
- **If-Else**: Conditional execution.
  ```php
  if ($a > $b) {
      echo "a is greater than b";
  } else {
      echo "a is not greater than b";
  }
  ```
- **Switch**: Select execution based on value.
  ```php
  switch ($color) {
      case "red":
          echo "Red";
          break;
      case "blue":
          echo "Blue";
          break;
      default:
          echo "No color";
  }
  ```
- **Loops**: `for`, `foreach`, `while`, `do-while`.
  ```php
  for ($i = 0; $i < 5; $i++) {
      echo $i;
  }
  ```

**Functions:**
- Declared with the `function` keyword.
- Can return values using `return`.
  ```php
  function add($x, $y) {
      return $x + $y;
  }
  ```

**Superglobals:**
- Predefined variables in PHP.
- Examples: `$_GET`, `$_POST`, `$_SESSION`, `$_COOKIE`, `$_SERVER`, `$_REQUEST`.

**Form Handling:**
- Use `$_GET` and `$_POST` to access form data.
  ```php
  $name = $_POST['name'];
  ```

**Database Interaction:**
- PHP supports several databases (MySQL, PostgreSQL, etc.).
- Use `mysqli` or `PDO` for database operations.
  ```php
  $conn = new mysqli($servername, $username, $password, $dbname);
  ```

**Error Handling:**
- Use `try-catch` for exceptions.
  ```php
  try {
      // Code that may throw an exception
  } catch (Exception $e) {
      echo 'Caught exception: ',  $e->getMessage(), "\n";
  }
  ```

**Object-Oriented Programming (OOP):**
- Classes and objects to encapsulate data and functions.
- Access modifiers: `public`, `private`, `protected`.
  ```php
  class Car {
      public $color;
      function __construct($color) {
          $this->color = $color;
      }
  }
  ```

**Common Functions:**
- `echo` and `print`: Output text.
- `include` and `require`: Include files.
- `isset()`: Check if a variable is set.
- `empty()`: Check if a variable is empty.

**Best Practices:**
- Use meaningful variable and function names.
- Separate logic and presentation.
- Use prepared statements to prevent SQL injection.
- Keep code DRY (Don't Repeat Yourself).

## Security related functions for Input Validation and Sanitization
1. **`filter_var()`**: 
   - Used for both validation and sanitization. 
   - Example filters: `FILTER_VALIDATE_EMAIL`, `FILTER_SANITIZE_STRING`, etc.

2. **`htmlspecialchars()`**: 
   - Converts special characters to HTML entities to prevent XSS attacks.

3. **`htmlentities()`**: 
   - Converts all applicable characters to HTML entities.

4. **`strip_tags()`**: 
   - Removes HTML and PHP tags from a string.

5. **`addslashes()`**: 
   - Escapes special characters in a string for use in SQL queries.
   - Note: Prefer using prepared statements or PDO for database interactions.

6. **`mysqli_real_escape_string()`**: 
   - Escapes special characters in a string for use in an SQL statement in MySQL.

7. **`password_hash()`**: 
   - Creates a password hash using a strong one-way hashing algorithm.

8. **`password_verify()`**: 
   - Verifies that a password matches a hash.

9. **`filter_input()`**: 
   - Fetches a specific external variable by name and optionally filters it.

10. **`hash_hmac()`**: 
    - Generates a keyed hash value using the HMAC method for data integrity checks.


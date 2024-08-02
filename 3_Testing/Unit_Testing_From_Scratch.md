## Writing Custom Unit Testing from Scratch

- Lets suppose we have a following function for which we need to run the Unit test

- Let's say filename is `calculator.php`
```
<?php

function add( $a, $b )
{
    return $a + $b;
}

?>
```

1. Step 1: Create `test-methods.php`

This file will be command for all the future Unit test cases

```
<?php

function expect_to_be_equal( $expected, $value)
{
    if ($expected === $value ) {
        return true;
    }

    throw new Exception(
        join(
            PHP_EOL,
            [
            "Expected Value = {$expected}",
            "Passed Value = {$value}",
            ]
        )
    );
}

function test( $text, callable $function )
{
    try {
        call_user_func($function);
        echo "PASS: {$text}" . PHP_EOL;
    } catch( Exception $e) {
        echo "FAIL: {$text}" . PHP_EOL;
        echo $e->getMessage();
    }
}
```

2. Step 2: Create `test-calculator.php`

Using the methods which are declared inside `test-methods.php`, we will be creating a Unit test for `calculator.php`

```
<?php

require_once 'test-methods.php';
require_once 'calculator.php';

test(
    "When 2 and 3 are summed, should return 5", function () {
        $result = add(2, 3);

        expect_to_be_equal(5, $result);
    }
);

?>
```



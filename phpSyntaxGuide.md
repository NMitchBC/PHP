<!-- Create a new MD document on Github called the PHP Syntax Guide

Create and describe each of the following parts of PHP. The guide should provide an example and description of the following PHP syntax categories. -->

# PHP Syntax Guide

### PHP Comments

- Comments allow others or yourself to know what is supposed to be going on in the code

```
// Single Line Comments
/* Multi Line Comments */
```

ie:

```
// These are not the Droids you are looking for.

/*  A Long time ago, in a galaxy far far away.
There exits a war between good & evil, light & dark.
The Jedi represemt the Light Side of the force & the Sith the Dark Side.
*/
```

### PHP Variables

Variables are "containers" for storing data.

A Variable Name must:

- start with the $ sign followed by the variable name
- start with a letter or the underscore character
- cannot start with a number
- can only contain alpha-numeric characters and underscores (A-z, 0-9, and \_ )
- are case-sensitive ($neil and $NEIL are two different variables)

ie:

```
<?php
$x = "Marvin the Paranoid Android";
$y = 54;
$somebodyElsesProblem = "aCouch";
?>
```

### PHP Echo / Print

- Echo and print are both used to output data to the screen

- Echo can accept multiple parameters, and has no return value. Echo is faster than print.

- Print can only accept one argument, and has a return value of 1, making it useful in expressions.

**Echo:**

```
<?php
    $variable = "You can include variables in echo statements.";

    echo $variable;
    echo "This outputs a string.";
    echo "<p>You can also include HTML in an echo statement.</p>"
?>
```

**Print:**

```
<?php
$txt1 = "Learn the Meaning of Lif";
$txt2 = "ZaphodBeeblebrox.com";
$x = 40;
$y = 2;

print "<h2>" . $txt1 . "</h2>";
print "Study The Impermanence of the World you know at " . $txt2 . "<br>";
print $x + $y;
?>
```

### PHP Data Types

The following data types are supported in PHP:

- Variables can store data of different types, and different data types can do different things.

```
Var_dump // This function returns the data type & it's value
```

ie:

```
$x = 5;
var_dump($x);
```

PHP supports the following data types:

- Strings
- Integers
- Floating Point Numbers
- Booleans
- Arrays
- Objects
- NULL
- Resource

#### Strings

- a string is a sequence of charachters, ie: "Any text written between quotes"

```
<?php
$x = "Luke Skywalker";
echo "$x";
?>
```

#### Integers

- An integer data type is a non-decimal number between -2,147,483,648 and 2,147,483,647.
- They can be specified in: decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation

```
<?php
$x = "123456789";
var_dump($x);
?>
```

#### Floating Point Numbers

- A floating point number is a number with a decimal point or a number in exponential form.

```
<?php
$x = "12.345";
var_dump($x);
?>
```

#### Booleans

- A Boolean represents two possible states: 1 = TRUE and 0 = FALSE.

```
<?php
$x = "false";
var_dump($x);
?>
```

#### Arrays

- An array stores multiple values in one single variable.

```
<?php
$spaceShips = array("Rocinante","Galactica","Enterprise");

echo $spaceShips;
?>
```

#### Objects

- Classes and objects are the two main aspects of object-oriented programming.
  A class is a template for objects, and an object is an instance of a class.

When individual objects are created, they inherit all the properties and behaviors from the class, but each object will have different values for the properties.

```
<?php
class Robot {
  public $color;
  public $model;
  public function __construct($color, $model) {
    $this->color = $color;
    $this->model = $model;
  }
  public function message() {
    return "My Killer Robot is a " . $this->color . " " . $this->model . "!";
  }
}

$myRobot = new BattleBot("red", "PlanetSmasher");
var_dump($myRobot);
?>
```

#### NULL

- Null is a special data type which can have only one value: NULL.
  A variable of data type NULL is a variable that has no value assigned to it.
  If a variable is created without a value, it is automatically assigned a value of NULL.
  Variables can also be emptied by setting the value to NULL:

```
<?php
$x = "To Infinity and Beyond!";
$x = null;
var_dump($x);
?>
```

#### Resource

### PHP Strings

- a string is a sequence of charachters, ie: "Any text written between quotes"
  they can be contained in single or double quotation marks

```
<?php
$x = "Han Solo";
echo "$x";
?>
```

##### Escape Sequences

|      |                 |
| ---- | --------------- |
| \n   | Linefeed        |
| \r   | Carriage Return |
| \t   | Horizontal Tab  |
| \v   | Vertical Tab    |
| \e   | Escape          |
| \f   | Form Feed       |
| \\\\ | Backslash       |
| \$   | Dollar Sign     |
| /'   | Single Quote    |
| \"   | Double Quote    |

#### String Functions:

A few examples of the many, many prebuilt string functions is as follows:

##### str_replace()

The str_replace() function replaces some characters with some other characters in a string.

```
str_replace(find,replace,string,count)
```

##### str_word_count()

The PHP str_word_count() function counts the number of words in a string.

```
echo str_word_count("Hello world!");
```

##### strpos()

The PHP strpos() function searches for a specific text within a string.

If a match is found, the function returns the character position of the first match. If no match is found, it will return FALSE.

```
echo strpos("Hello world!", "world");
```

##### strlen()

    Returns the length of a string

### PHP Numbers

- There are 3 main nunber types:
  Integers, Floating Point Numbers, Number Strings.
- there is also Infinite & NAN

#### Integer

An integer is a non-decimal number between -2,147,483,648 and 2,147,483,647.

Integers:

- must have at least one digit
- must not have a decimal point
- can be either positive or negative
- can be specified in: decimal (base 10), hexadecimal (base 16), octal (base 8), or binary (base 2) notation

Use var_dump() to find the type

```
<?php
$x = "123456789";
var_dump($x);
?>
```

You can use the following to see if a variable is an Integer

```
is_int()
is_integer()
is_long()
```

#### Floating Point Number

- A floating point number is a number with a decimal point or a number in exponential form.

```
<?php
$x = "12.345";
var_dump($x);
?>
```

```
$x = 10.365;
var_dump(is_float($x));
```

#### Infinite Numbers

numeric value that is larger than PHP_FLOAT_MAX is considered infinite.

PHP has the following functions to check if a numeric value is finite or infinite:

```
is_finite()
is_infinite()
```

The PHP var_dump() function returns the data type and value:

#### NAN (Not A Number)

- NaN is used for impossible mathematical operations.
- PHP has the following functions to check if a value is not a number:

: is_nan()

The PHP var_dump() function returns the data type and value:

### PHP Constants

- A constant is a variable that can't be changed during the script.
- A valid constant name starts with a letter or underscore (no $ sign before the constant name).
- To create a constant, use the define() function.
- you can use define to make a array constant
- You can also use the const keyword

**const vs. define():**

const is always case-sensitive
define() has a case-insensitive option.
const cannot be created inside another block scope, like inside a function or inside an if statement.
define can be created inside another block scope.

```
define("Hello", "Hello there, Where do you think you're going?");
echo Hello;

function greeting() {
echo Hello;
}

greeting();
```

```
define("boats", ["Jolly Roger", "Endurance", "Terror"]);
echo boats[0];
```

or:

```
const myBoat = "Awesome Sauce";
echo myBoat;
```

### PHP Operators

- Operators are used to perform operations on variables and values.

PHP divides the operators in the following groups:

#### Arithmetic operators

The PHP arithmetic operators are used with numeric values to perform common arithmetical operations, such as addition, subtraction, multiplication, division, modulus, exponents etc.

ie:

- if:
- $x = 42
- $y = 7

| Operator | Name           | Example                                 |
| -------- | -------------- | --------------------------------------- |
| +        | Addition       | $x + $y // returns 49                   |
| -        | Subtraction    | $x - $y // returns 35                   |
| \*       | Multiplication | x \* y // returns 294                   |
| /        | Division       | $x / $y // returns 6                    |
| %        | Modulo         | $y % $x // returns 0                    |
| \*\*     | Exponentiation | y \*\* x // returns a really big number |

#### Assignment operators

The PHP assignment operators are used with numeric values to write a value to a variable.

The basic assignment operator in PHP is "=". It means that the left operand gets set to the value of the assignment expression on the right.

ie:
: x = y

Assignment Operators are used to write values to variables.

| Assignment | Same as    |
| ---------- | ---------- |
| a += b     | a = a + b  |
| a -= b     | a = a - b  |
| a \*= b    | a = a \* b |
| a /= b     | a = a / b  |
| a %= b     | a = a % b  |

#### Comparison operators

The PHP comparison operators are used to compare two values (number or string):

| Operator | Name                                 |
| -------- | ------------------------------------ |
| ==       | Equal                                |
| ===      | Not Equal                            |
| !=       | Not Identical                        |
| <>       | Less Than                            |
| !==      | Greater Than                         |
| <        | Less Than                            |
| >        | Greater Than                         |
| <=       | Less Than or Equal To                |
| >=       | Greater Than or Equal To             |
| <=>      | Less Than, Equal To, or Greater Than |

ie: $x != $y
x does not equal y

#### Increment/Decrement operators

The PHP increment operators are used to increment a variable's value.

ie:
: $x++ returns a variable and then increments it by one

The PHP decrement operators are used to decrement a variable's value.

ie:
: --$x will decrement the variable by one & then return it

#### Logical operators

The PHP logical operators are used to combine conditional statements.

| Operator | Name         |
| -------- | ------------ |
| and      | And          |
| or       | Or           |
| xor      | Exclusive Or |
| !        | Not          |
| &&       | And          |
| \|\|     | Or           |

#### String operators

PHP has two operators that are specially designed for strings.

ie:
: $x . $y
to concatenate x & y
: $x .= $y
to append $y to $x

#### Array operators

The PHP array operators are used to compare arrays.

ie: $x == $y
true if both are the same

#### Conditional assignment operators

The PHP conditional assignment operators are used to set a value depending on conditions:

### PHP If & Else & Elseif

Operators from above work here as well

##### IF:

Executes some code if one condition is true

```
if (condition) {
 // code to execute if condition is met
}
```

ie:

```
<?php
$t = date("H");

if ($t < "20") {
  echo "Have a good day!";
}
?>
```

##### If..ELSE:

Executes some code if a condition is true and another code if that condition is false

```
if (condition) {
 // code to execute if condition is met
} else {
 // code to execute if condition is not met
}
```

ie:

```
<?php
$t = date("H");

if ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>
```

##### If.. ELSE IF.. Else

Executes different codes for more than two conditions

```
if (condition) {
 // code to execute if condition is met
} elseif (condition) {
 // code to execute if this condition is met
} else {
 // code to execute if none of the conditions are met
}
```

ie:

```
<?php
$t = date("H");
echo "<p>The hour (of the server) is " . $t;
echo ", and will give the following message:</p>";

if ($t < "10") {
  echo "Have a good morning!";
} elseif ($t < "20") {
  echo "Have a good day!";
} else {
  echo "Have a good night!";
}
?>
```

### PHP Functions

**Built In Functions**

- PHP has over 1000 built-in functions that can be called directly, from within a script, to perform a specific task.

**User-Defined Functions**

- A function is a block of statements that can be used repeatedly in a program.
- will not execute automatically when a page loads.
- will be executed by a call to the function.
  -name must start with a letter or an underscore. Function names are NOT case-sensitive

**Creating a Function**

- A user-defined function declaration starts with the keyword function, followed by the name of the function:

```

function myQuestion{
echo "What is the average flight speed on of unladen swallow!";
}

myQuestion();

```

**Function Parameters or Arguments**

- Information can be passed to functions through arguments. An argument is just like a variable.

Arguments are specified after the function name, inside the parentheses. You can add as many arguments as you want, just separate them with a comma.

- To let a function return a value, use the return statement:

### PHP Arrays

- An array is a special variable that can hold many values under a single name, and you can access the values by referring to an index number or name.

- In PHP, there are three types of arrays:

**Indexed arrays:**

- Arrays with a numeric index

```
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
?>
```

**Associative arrays:**

```
- Arrays with named keys
  <?php
  $age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
  echo "Peter is " . $age['Peter'] . " years old.";
  ?>
```

**Multidimensional arrays:**

- Arrays containing one or more arrays

Array items can be of any data type.
The most common are strings and numbers (int, float), but array items can also be objects, functions or even arrays.
You can have different data types in the same array.

**An Array:**

```
<?php
    $powers = array("Flight", "Super Strength", "Teleportation");

    echo "What is your favorite Super Power? Is it " . $powers[0] . ", " .
    $powers[1] . " or " . $powers[2] . "?";
?>

// outputs "What is your favorite Super Power? Is it Flight, Super Strength or Teleportation?"
```

### PHP Loops

- Loops are used to execute the same block of code again and again, as long as a certain condition is true.

In PHP, we have the following loop types:

while - loops through a block of code as long as the specified condition is true
do...while - loops through a block of code once, and then repeats the loop as long as the specified condition is true
for - loops through a block of code a specified number of times
foreach - loops through a block of code for each element in an array

#### While Loop

The while loop executes a block of code as long as the specified condition is true.

```
while (condition that must apply) {
 // code to execute goes here
}
```

```
$x = 1;

while($x <= 5) {
  echo "The number is: $x <br>";
  $x++;
}
?>
```

#### Do While Loop

- The do...while loop will always execute the block of code at least once, it will then check the condition, and repeat the loop while the specified condition is true.

```
do {
 // code to execute goes here;
} while (condition that must apply);
```

```
<?php
$x = 1;

do {
  echo "The number is: $x <br>";
  $x++;
} while ($x <= 5);
?>
```

#### For Loop

The for loop - Loops through a block of code a specified number of times.

```

for ($x = 0; $x <= 10; $x++) {
echo "The number is: $x <br>";
}

```

#### Foreach Loop

- The foreach loop - Loops through a block of code for each element in an array or each property in an object.
- The most common use of the foreach loop, is to loop through the items of an array.

```

<?php
$colors = array("red", "green", "blue", "yellow");

foreach ($colors as $x) {
  echo "$x <br>";
}
?>

```

#### Break

The break statement can be used to jump out of different kind of loops.
We can stop the loop even if the condition is still true:

```

for ($x = 0; $x < 10; $x++) {
  if ($x == 4) {
break;
}
echo "The number is: $x <br>";
}

```

#### Continue

The continue statement can be used to jump out of the current iteration of a loop, and continue with the next.

ie:

```

for ($x = 0; $x < 10; $x++) {
  if ($x == 4) {
continue;
}
echo "The number is: $x <br>";
}

```

#### Error checking Easter Egg:

Insert this at the beginning of the php page & it will output to the page of any errors upon loading

```

<?php
// PHP Error Display

ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
?>

```

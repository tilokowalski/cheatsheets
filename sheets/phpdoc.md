# PHPDoc

This document categorizes PHPDoc tags and provides detailed descriptions along with example usage for each tag.

## General Example

  ```php
  /**
   * Finds the maximum value in an array.
   *
   * Iterates through each element of the array, comparing each value with the current maximum. 
   * If a larger value is found, it updates the maximum. Throws an exception if the array is empty.
   *
   * @param array $numbers An array of integers to search for the maximum value.
   * 
   * @return int $max The maximum value found in the array.
   * 
   * @throws InvalidArgumentException If the input array is empty.
   */
  function findMaxInArray(array $numbers) {
      if (empty($numbers)) {
          throw new InvalidArgumentException('Input array cannot be empty.');
      }

      $max = $numbers[0];

      foreach ($numbers as $num) {
          if ($num > $max) {
              $max = $num;
          }
      }

      return $max;
  }
  ```

# Tag Reference

## Any
These tags can be used in any PHPDoc context.

### `@deprecated`
- **Description**: Indicates that the method, class, function, or property is deprecated and should not be used.
- **Example**:

  ```php
  /**
   * @deprecated Use newFunction() instead.
   */
  function oldFunction() {}
  ```

### `@since`
- **Description**: Specifies the version when the element was added to the codebase.
- **Example**:

  ```php
  /**
   * @since 2.0.0
   */
  class NewClass {}
  ```

### `@see`
- **Description**: Creates a reference to a related piece of code, such as another method, class, or documentation.
- **Example**:

  ```php
  /**
   * @see OtherClass::otherFunction() For related functionality.
   */
  function someFunction() {}
  ```

### `@link`
- **Description**: Provides a URL for additional information or external documentation.
- **Example**:

  ```php
  /**
   * @link https://www.example.com More information.
   */
  class ExampleClass {}
  ```

### `@todo`
- **Description**: Marks a task or feature that needs to be implemented or refined in the code.
- **Example**:

  ```php
  /**
   * @todo Implement this function.
   */
  function futureFunction() {}
  ```

### `@example`
- **Description**: Provides an example of how the code should be used.
- **Example**:

  ```php
  /**
   * @example $object = new MyClass();
   */
  class MyClass {}
  ```

### `@author`
- **Description**: Identifies the author of the piece of code.
- **Example**:

  ```php
  /**
   * @author John Doe
   */
  class AuthoredClass {}
  ```

### `@license`
- **Description**: Indicates the licensing information under which the code is released.
- **Example**:

  ```php
  /**
   * @license MIT
   */
  function licensedFunction() {}
  ```

## Classes / Interfaces
Primarily used with classes or interfaces.

### `@method`
- **Description**: Describes a method in a class, especially used for magic methods in classes using the `__call` magic method.
- **Example**:

  ```php
  /**
   * @method string getString() Returns a string
   */
  class MyClass {}
  ```

### `@property`
- **Description**: Describes a property in a class, especially used for magic properties in classes using the `__get` and `__set` magic methods.
- **Example**:

  ```php
  /**
   * @property int $id Identifier
   */
  class MyClass {}
  ```

## Properties
Used with class properties.

### `@var`
- **Description**: Documents the type of a class property.
- **Example**:

  ```php
  class MyClass {
    /**
     * @var string $property Description of the property.
     */
    public string $property;
  }
  ```

## Methods
Used with methods and functions.

### `@param`
- **Description**: Describes a parameter of a function or method, including its type and purpose.
- **Example**:

  ```php
  /**
   * @param string $param Description of the parameter.
   */
  function myFunction(string $param) {}
  ```

### `@return`
- **Description**: Specifies the type and description of the return value of functions and methods.
- **Example**:

  ```php
  /**
   * @return int The result of the calculation.
   */
  function calculate() {}
  ```

### `@throws`
- **Description**: Indicates the exceptions that a function or method may throw.
- **Example**:

  ```php
  /**
   * @throws Exception When something goes wrong.
   */
  function riskyFunction() {}
  ```

### `@inheritdoc`
- **Description**: Indicates that the documentation for a method or property should be inherited from the parent class or interface.
- **Example**:

  ```php
  class ChildClass extends ParentClass {
    /**
     * @inheritdoc
     */
    public function inheritedMethod() {}
  }
  ```

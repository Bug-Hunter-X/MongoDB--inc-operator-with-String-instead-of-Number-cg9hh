# MongoDB $inc operator with String instead of Number

This example demonstrates an uncommon error when using the `$inc` operator in MongoDB update operations.  The `$inc` operator is designed to increment a numeric field by a specified value.  However, providing a string value instead of a number leads to incorrect behavior.

## Bug Description
The bug arises from using a string ('1') instead of a number (1) as the increment value with the `$inc` operator. This results in the update operation either failing completely or leading to unexpected results, potentially corrupting data.

## Bug Solution
The solution is simple: always use a numerical value with the `$inc` operator. Ensure the field being incremented is also of a numeric type (int, long, double) in your MongoDB schema.

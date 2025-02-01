# Uninitialized Property Access in C#

This repository demonstrates a common yet subtle bug in C#: accessing a property before it has been explicitly initialized.  Uninitialized properties can lead to unexpected behavior, making debugging difficult.

The `bug.cs` file contains code exhibiting this problem.  The `bugSolution.cs` file presents a corrected version, showcasing best practices to avoid this issue.

## How to reproduce the bug

1. Clone this repository.
2. Open `bug.cs` in a C# IDE (like Visual Studio).
3. Run the code. Observe that the output might be 0 (the default value for an integer), which is not necessarily the intended value.

## Solution

The solution involves initializing the property either in the constructor or explicitly before accessing it. See `bugSolution.cs` for the corrected code.

## Best Practices

* **Always initialize properties:**  Explicitly set values to properties during object construction to prevent undefined values.
* **Use constructors for initialization:** This is generally the preferred method for setting initial property values.
* **Consider using nullable types:** If a property can legitimately be uninitialized, use nullable types (e.g., `int?`) to handle the possibility of a null value.  Use null-conditional operators to check for null values before accessing the property.

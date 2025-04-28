<!-- Project Header -->
<div align="center">
  <h1 class="projectName">MiniCalc C++</h1>

  <p class="projectBadges">
    <img src="https://johng.io/badges/category/App.svg" alt="Project category" title="Project category"/>
    <img src="https://img.shields.io/github/languages/top/jerboa88/calculator.svg" alt="Language" title="Language"/>
    <img src="https://img.shields.io/github/repo-size/jerboa88/calculator.svg" alt="Repository size" title="Repository size"/>
    <a href="LICENSE">
      <img src="https://img.shields.io/github/license/jerboa88/calculator.svg" alt="Project license" title="Project license"/>
    </a>
  </p>
  
  <p class="projectDesc">
    A C++ library for parsing and evaluating arithmetic expressions
  </p>
  
  <br/>
</div>


MiniCalc C++ is a simple but fast operator-precedence parser. It compiles with any C++ compiler and should work with any floating-point type in the future.


## Supported operators
```calculator.hpp``` uses the same operator precedence and associativity
as the C++ programming language and also supports the power operator.

<table>
	<tr align="center">
		<td><b>Operator</b></td>
		<td><b>Description</b></td>
	</tr>
	<tr align="left">
		<td>+</td>
		<td>Addition</td>
	</tr>
	<tr align="left">
		<td>-</td>
		<td>Subtraction</td>
	</tr>
	<tr align="left">
		<td>* or x</td>
		<td>Multiplication</td>
	</tr>
	<tr align="left">
		<td>/</td>
		<td>Division</td>
	</tr>
	<tr align="left">
		<td>%</td>
		<td>Modulo</td>
	</tr>
	<tr align="left">
		<td>^ or **</td>
		<td>Raise to power</td>
	</tr>
</table>


## C++ API
Functions defined in ```calculator.hpp```.
```C++
int calculator::eval(const std::string& expression);

template <typename T>
T calculator::eval<T>(const std::string& expression);
```

## How to use it
```calculator::eval("1+2")``` takes a string with an floating-point arithmetic expression as an argument, evaluates the arithmetic expression and returns
the result. If the expression string is not a valid floating-point arithmetic expression a ```calculator::error``` exception is thrown.

```C++
#include "calculator.hpp"
#include <stdint.h>
#include <iostream>
using namespace std;

int main() {
	try {
		int result = calculator::eval("(2^2+1)/3"); // 1.66666666667
		cout << result << endl;
	}
	catch (calculator::error& e) {
		cerr << e.what() << endl;
	}

	return 0;
}
```


## License
This project is licensed under the BSD 2-Clause License. See [LICENSE](LICENSE) for details.

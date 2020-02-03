# Code Smell

Code smells are usually not bugs they are not technically incorrect and do not prevent the program from functioning. Instead, they indicate **weaknesses in design** that may slow down development or **increase** the risk of bugs or **failures in the future**.

#### **Application-level smells:**

* _Duplicated code_: identical or very similar code exists in more than one location.
* _Contrived complexity_: forced usage of overcomplicated design patterns where simpler design would suffice.
* _Shotgun surgery_: a single change needs to be applied to multiple classes at the same time.

#### **Class-level smells:**

* _Large class_: a class that has grown too large.
* \*Lazy class: a class that does too little.
* _Cyclomatic complexity_: too many branches or loops; this may indicate a function needs to be broken up into smaller functions, or that it has potential for simplification.

#### Method-level smells:

* _Too many parameters_: a long list of parameters is hard to read, and makes calling and testing the function complicated. It may indicate that the purpose of the function is ill-conceived and that the code should be refactored so responsibility is assigned in a more clean-cut way.
* _Long method_: a method, function, or procedure that has grown too large.
* _Excessive return of data_: a function or method that returns more than what each of its callers needs.
* _Excessively long line of code_ \(or God Line\): A line of code which is so long, making the code difficult to read, understand, debug, refactor, or even identify possibilities of software reuse.


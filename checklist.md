# Checklist for Databse application

If stuck or ready you can check below expectations.

<details><summary>Separate header and source files for classes</summary>
<p>

- Files: Student.hpp, Student.cpp, Employee.cpp, Employee.hpp, Person.cpp, Person.hpp, Database.cpp, Database.hpp, main.cpp (names can differ of course)
- Optional PeselValidation.hpp and/or PeselValidation.cpp. It may also be a part of Database.

</p>
</details>

<details><summary>Person.hpp</summary>
<p>

- Name, surname and address should be strings
- Gender should be an enum
- No default constructor
- Virtual destructor
- Should have common fields: name, lastName, pesel, gender, address
- All fields should be private
- Should have public setAddress function
- Should have serialization function eg. toString to make displaying and saving easier

</p>
</details>

<details><summary>Person.cpp</summary>
<p>

- Fields should be filled on constructor initilization list

</p>
</details>

<details><summary>Employee.hpp</summary>
<p>

- Should have private salary field
- Should have public getSalary const function
- Should have public setSalary function

</p>
</details>

<details><summary>Employee.cpp</summary>
<p>

- Constructor should call base class constructor

</p>
</details>

<details><summary>Student.hpp</summary>
<p>

- Should have private index field
- Should have public getIndex const function

</p>
</details>

<details><summary>Student.cpp</summary>
<p>

- Constructor should call base class constructor

</p>
</details>

<details><summary>Database.hpp</summary>
<p>

- Should have a container of pointers to Person (or smart pointers to Person)
- Should have alias using on a container (or typedef)
- The container should be a private field in Database class
- Can have NotFound exception
- Should have functions like add, find, show/display, sort, generate, save, load, remove, modifySalary, modifyAddress
- Should have isValid(pesel) function returning bool

</p>
</details>

<details><summary>Database.cpp</summary>
<p>

- Find can use std::find or std::find_if
- Show/display should call serialization method on every person, not get every field here.
- Sort should use std::sort
- Save should also use serialization function to avoid duplication
- Remove should use std::remove_if and erase functions
- Streams should be used for serialization (displaying, saving, loading)

</p>
</details>

<details><summary>main.cpp</summary>
<p>

- Should use assertions to check validity of the program
- Can use assertions for checking pesel like below one: (just copy and adjust to your program)

```cplusplus
     assert(not isPeselValid("1234567a901", Gender::Female) && "not a digit");
     assert(not isPeselValid("12345678901", Gender::Female) && "invalid month");
     assert(not isPeselValid("12325678901", Gender::Female) && "invalid day");
     assert(not isPeselValid("03222978901", Gender::Female) && "not leap year");
     assert(not isPeselValid("04222978911", Gender::Female) && "not a female");
     assert(not isPeselValid("04222978901", Gender::Male) && "not a male");
     assert(not isPeselValid("04222978901", Gender::Female) && "invalid checksum");
     assert(isPeselValid("04222978907", Gender::Female) && "valid");
```

</p>
</details>

# Technical MCQ Q&A for SDET Preparation

## SECTION 1: OOP CONCEPTS

**Q1.** Which OOP concept is demonstrated when a subclass provides a specific implementation of a method that is already provided by its parent class?
- A) Method Overloading
- B) Method Overriding
- C) Encapsulation
- D) Abstraction

**Answer: B) Method Overriding**
**Explanation:** Method overriding allows a subclass to provide a specific implementation of a method that is already provided by one of its superclasses. It is an example of runtime polymorphism.

**Q2.** What is the primary difference between an Abstract Class and an Interface in Java?
- A) An abstract class can have abstract methods, but an interface cannot.
- B) An interface can have constructors, but an abstract class cannot.
- C) An abstract class can have state (instance variables), while an interface traditionally only has static final constants.
- D) A class can inherit multiple abstract classes but implement only one interface.

**Answer: C) An abstract class can have state (instance variables), while an interface traditionally only has static final constants.**
**Explanation:** Abstract classes can have instance variables and constructors. A class can implement multiple interfaces, but only extend one abstract class.

**Q3.** Which SOLID principle states that a class should have only one reason to change?
- A) Single Responsibility Principle
- B) Open/Closed Principle
- C) Liskov Substitution Principle
- D) Dependency Inversion Principle

**Answer: A) Single Responsibility Principle**
**Explanation:** SRP states that every class should have a single responsibility, reducing coupling and making the system easier to maintain.

**Q4.** Which design pattern ensures that only one instance of a class is created in the Java Virtual Machine?
- A) Factory Pattern
- B) Observer Pattern
- C) Singleton Pattern
- D) Builder Pattern

**Answer: C) Singleton Pattern**
**Explanation:** The Singleton pattern restricts the instantiation of a class to one "single" instance.

**Q5.** How is encapsulation primarily achieved in Java?
- A) By making variables public and methods private.
- B) By using the 'final' keyword.
- C) By making variables private and providing public getter and setter methods.
- D) By extending a superclass.

**Answer: C) By making variables private and providing public getter and setter methods.**
**Explanation:** Encapsulation hides the internal state of an object and requires all interaction to be performed through an object's methods.

**Q6.** Which type of binding occurs during compile time?
- A) Dynamic Binding
- B) Static Binding
- C) Late Binding
- D) Runtime Binding

**Answer: B) Static Binding**
**Explanation:** Static binding (or early binding) happens at compile time, typically used with private, final, and static methods and method overloading.

**Q7.** The 'Diamond Problem' is an ambiguity that arises primarily in languages that support:
- A) Multiple inheritance of classes
- B) Single inheritance
- C) Multilevel inheritance
- D) Interfaces

**Answer: A) Multiple inheritance of classes**
**Explanation:** If a class inherits from two classes that have a common ancestor, and both provide an implementation of a method, the compiler doesn't know which to use.

**Q8.** Dependency Injection is a technique used to implement which SOLID principle?
- A) Single Responsibility Principle
- B) Interface Segregation Principle
- C) Liskov Substitution Principle
- D) Dependency Inversion Principle

**Answer: D) Dependency Inversion Principle**
**Explanation:** Dependency Injection supplies the dependencies of an object rather than letting the object create them itself, fulfilling the Dependency Inversion Principle.

**Q9.** In object-oriented design, what is 'Composition'?
- A) An "is-a" relationship where a child class inherits from a parent class.
- B) A "has-a" relationship where a class contains objects of other classes.
- C) A method of grouping identical methods in an interface.
- D) The process of casting a child object to a parent reference.

**Answer: B) A "has-a" relationship where a class contains objects of other classes.**
**Explanation:** Composition is preferred over inheritance to achieve code reuse without the tight coupling that inheritance brings.

**Q10.** What does high cohesion in a software module mean?
- A) The module depends heavily on other modules.
- B) The module has a single, well-defined purpose.
- C) The module contains methods that are unrelated.
- D) The module is difficult to test in isolation.

**Answer: B) The module has a single, well-defined purpose.**
**Explanation:** High cohesion means that the elements within a module belong strongly together, focused on a specific task.

**Q11.** Which access modifier makes a member accessible only within its own package and subclasses?
- A) private
- B) default (package-private)
- C) protected
- D) public

**Answer: C) protected**
**Explanation:** The protected modifier allows access within the same package and to subclasses in other packages.

**Q12.** What is constructor chaining?
- A) Calling a constructor from another method.
- B) Calling one constructor from another constructor within the same class or a superclass.
- C) Overriding a superclass constructor.
- D) Making a constructor abstract.

**Answer: B) Calling one constructor from another constructor within the same class or a superclass.**
**Explanation:** In Java, `this()` is used to call a constructor in the same class, and `super()` is used to call a superclass constructor.

**Q13.** Which design pattern is used to define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified?
- A) Strategy
- B) Observer
- C) Factory
- D) Singleton

**Answer: B) Observer**
**Explanation:** The Observer pattern is highly used in event-handling systems where listeners subscribe to an event source.

**Q14.** Abstraction is achieved in Java by using:
- A) Abstract classes and interfaces.
- B) Encapsulation and inheritance.
- C) Try-catch blocks.
- D) Method overloading.

**Answer: A) Abstract classes and interfaces.**
**Explanation:** Abstraction hides the complex implementation details and shows only the essential features of the object.

**Q15.** Which statement about Method Overloading is false?
- A) It occurs within the same class.
- B) Methods must have the same name.
- C) Methods must have the same parameter list.
- D) Return type can be different.

**Answer: C) Methods must have the same parameter list.**
**Explanation:** For method overloading, methods must have the same name but DIFFERENT parameter lists (number, type, or order of parameters).

---

## SECTION 2: JAVA CODE OUTPUT / SNIPPET QUESTIONS

**Q1.** What is the output of the following code?
```java
String s1 = "hello";
String s2 = new String("hello");
System.out.println(s1 == s2);
System.out.println(s1.equals(s2));
```
- A) true, true
- B) false, true
- C) true, false
- D) false, false

**Answer: B) false, true**
**Explanation:** `==` checks for reference equality. `s1` is in the string pool, `s2` is a new object in the heap. `.equals()` checks for value equality, which is true.

**Q2.** Which of the following is true about ArrayList vs LinkedList?
- A) LinkedList is faster for random access.
- B) ArrayList is implemented as a doubly-linked list.
- C) LinkedList is generally faster for inserting/deleting elements in the middle of the list.
- D) ArrayList has higher memory overhead per element.

**Answer: C) LinkedList is generally faster for inserting/deleting elements in the middle of the list.**
**Explanation:** ArrayList is backed by an array, so inserting in the middle requires shifting elements. LinkedList only requires changing pointer references.

**Q3.** What happens if a HashMap encounters a hash collision?
- A) It throws a CollisionException.
- B) It overwrites the old value.
- C) It stores the new key-value pair in a linked list (or tree) at that bucket index.
- D) It automatically resizes the map.

**Answer: C) It stores the new key-value pair in a linked list (or tree) at that bucket index.**
**Explanation:** HashMap uses separate chaining. If keys hash to the same bucket, they are stored in a linked list (or a balanced tree if the bin gets too large).

**Q4.** What is the output?
```java
Integer a = 100; Integer b = 100;
Integer c = 500; Integer d = 500;
System.out.println(a == b);
System.out.println(c == d);
```
- A) true, true
- B) false, false
- C) true, false
- D) false, true

**Answer: C) true, false**
**Explanation:** Java caches Integer objects in the range -128 to 127 during autoboxing. Thus `a` and `b` point to the same object, while `c` and `d` create new objects.

**Q5.** In what order do the blocks execute if an exception is thrown in `try` and caught in `catch`?
- A) try -> finally -> catch
- B) try -> catch -> finally
- C) try -> finally
- D) catch -> finally -> try

**Answer: B) try -> catch -> finally**
**Explanation:** The `try` block executes until the exception, then control jumps to the `catch` block, and finally the `finally` block executes regardless of whether an exception occurred.

**Q6.** Which keyword is used to prevent a variable from being modified?
- A) static
- B) abstract
- C) final
- D) volatile

**Answer: C) final**
**Explanation:** The `final` keyword makes a variable a constant. For methods, it prevents overriding. For classes, it prevents inheritance.

**Q7.** What exception is thrown if you try to call a method on a null reference?
- A) NullReferenceException
- B) NullPointerException
- C) IllegalStateException
- D) IllegalArgumentException

**Answer: B) NullPointerException**
**Explanation:** In Java, attempting to dereference a null object reference results in a `NullPointerException`.

**Q8.** What is the difference between `Comparable` and `Comparator`?
- A) Comparable is in `java.util`, Comparator is in `java.lang`.
- B) Comparable provides a single sorting sequence, Comparator provides multiple sorting sequences.
- C) Comparable modifies the original class, Comparator cannot be used on custom classes.
- D) They are identical in function.

**Answer: B) Comparable provides a single sorting sequence, Comparator provides multiple sorting sequences.**
**Explanation:** `Comparable` uses `compareTo()` inside the class itself. `Comparator` uses `compare()` in a separate class, allowing for customized external sorting logic.

**Q9.** Can an overriding method in a subclass throw a broader checked exception than the overridden method in the superclass?
- A) Yes, always.
- B) Yes, but only if it's a RuntimeException.
- C) No, it can only throw the same exception, a narrower checked exception, or any unchecked exception.
- D) No, an overriding method cannot throw any exceptions.

**Answer: C) No, it can only throw the same exception, a narrower checked exception, or any unchecked exception.**
**Explanation:** Changing to a broader checked exception violates the contract of the superclass method.

**Q10.** What does the `static` keyword mean when applied to a method?
- A) The method can only be accessed by the class itself, not subclasses.
- B) The method belongs to the class rather than instances of the class.
- C) The method's return value cannot change.
- D) The method executes faster.

**Answer: B) The method belongs to the class rather than instances of the class.**
**Explanation:** Static methods are resolved at compile time and can be called without instantiating the class.

**Q11.** What happens if an element is added to an ArrayList at an index greater than its size?
- A) The ArrayList expands automatically.
- B) Null elements are inserted to fill the gap.
- C) IndexOutOfBoundsException is thrown.
- D) The element is added at the end.

**Answer: C) IndexOutOfBoundsException is thrown.**
**Explanation:** You cannot add elements at arbitrary indexes beyond the current size of the list; the index must be `<= size()`.

**Q12.** What is the main difference between `Iterator` and `ListIterator`?
- A) `Iterator` can traverse in both directions, `ListIterator` only forward.
- B) `ListIterator` can traverse in both directions and add elements, `Iterator` can only traverse forward and remove elements.
- C) `Iterator` is only for Maps, `ListIterator` is for Lists.
- D) There is no difference.

**Answer: B) `ListIterator` can traverse in both directions and add elements, `Iterator` can only traverse forward and remove elements.**
**Explanation:** `ListIterator` is specifically designed for lists and supports `previous()`, `hasPrevious()`, `add()`, and `set()`.

**Q13.** Which Stream API method is used to transform elements in a stream?
- A) filter()
- B) map()
- C) reduce()
- D) forEach()

**Answer: B) map()**
**Explanation:** The `map()` function takes a Function as an argument and applies it to each element, returning a stream of the transformed elements.

**Q14.** What does the `finalize()` method do?
- A) It makes a class immutable.
- B) It executes code just before the JVM shuts down.
- C) It is called by the garbage collector before an object is destroyed.
- D) It ensures a `try` block resources are closed.

**Answer: C) It is called by the garbage collector before an object is destroyed.**
**Explanation:** Note that `finalize()` is deprecated in newer Java versions because its execution is not guaranteed, but it was used for cleanup before GC.

**Q15.** What is the output of starting a new Thread using `run()` instead of `start()`?
- A) A new thread is created and executes the run method.
- B) It throws an IllegalThreadStateException.
- C) The run method executes in the current (calling) thread, not a new thread.
- D) Compilation error.

**Answer: C) The run method executes in the current (calling) thread, not a new thread.**
**Explanation:** Calling `run()` directly behaves like a normal method call. `start()` is required to actually spawn a new thread in the JVM.

---

## SECTION 3: PYTHON CODE OUTPUT / SNIPPET QUESTIONS

**Q1.** Which of the following data types in Python is immutable?
- A) list
- B) dict
- C) set
- D) tuple

**Answer: D) tuple**
**Explanation:** Tuples are immutable, meaning their elements cannot be changed after creation. Lists, dicts, and sets are mutable.

**Q2.** What is the output of `print([x * 2 for x in range(3)])`?
- A) [0, 2, 4]
- B) [2, 4, 6]
- C) [0, 1, 2]
- D) Error

**Answer: A) [0, 2, 4]**
**Explanation:** `range(3)` produces 0, 1, 2. The list comprehension multiplies each by 2, resulting in 0, 2, 4.

**Q3.** What is the difference between `==` and `is` in Python?
- A) `==` checks identity, `is` checks value.
- B) `==` checks value equality, `is` checks reference/identity equality.
- C) They are exactly the same.
- D) `is` is used only for booleans.

**Answer: B) `==` checks value equality, `is` checks reference/identity equality.**
**Explanation:** `==` compares the values of two objects, whereas `is` checks whether two variables point to the exact same object in memory.

**Q4.** What do `*args` and `**kwargs` do in a function definition?
- A) They are required arguments.
- B) `*args` takes a list of positional arguments, `**kwargs` takes a dictionary of keyword arguments.
- C) `*args` is for pointers, `**kwargs` is for double pointers.
- D) They unpack dictionaries.

**Answer: B) `*args` takes a list of positional arguments, `**kwargs` takes a dictionary of keyword arguments.**
**Explanation:** They allow a function to accept an arbitrary number of positional and keyword arguments.

**Q5.** What is a Python Decorator?
- A) A class that extends another class.
- B) A function that takes another function and extends its behavior without explicitly modifying it.
- C) A method to format strings.
- D) A module for UI design.

**Answer: B) A function that takes another function and extends its behavior without explicitly modifying it.**
**Explanation:** Decorators wrap a function, modifying its behavior (e.g., logging, timing) using the `@decorator_name` syntax.

**Q6.** How is a Generator different from a standard Iterator?
- A) Generators use the `return` keyword instead of `yield`.
- B) Generators store all values in memory.
- C) Generators use the `yield` keyword to produce values one at a time, suspending their state.
- D) There is no difference.

**Answer: C) Generators use the `yield` keyword to produce values one at a time, suspending their state.**
**Explanation:** Generators are memory efficient because they yield items one by one instead of generating an entire list in memory.

**Q7.** What is the Global Interpreter Lock (GIL) in Python?
- A) A security mechanism to prevent unauthorized code execution.
- B) A mutex that protects access to Python objects, preventing multiple threads from executing Python bytecodes at once.
- C) A tool for locking files during I/O operations.
- D) A garbage collection strategy.

**Answer: B) A mutex that protects access to Python objects, preventing multiple threads from executing Python bytecodes at once.**
**Explanation:** The GIL makes CPython thread-safe but prevents true parallel multi-threading for CPU-bound tasks.

**Q8.** What is the output of `my_list = [10, 20, 30, 40]; print(my_list[::-1])`?
- A) [10, 20, 30, 40]
- B) [40, 30, 20, 10]
- C) [40]
- D) IndexError

**Answer: B) [40, 30, 20, 10]**
**Explanation:** The slice notation `[::-1]` returns a new list with the elements in reverse order.

**Q9.** How do you handle exceptions in Python?
- A) try-catch-finally
- B) try-except-finally
- C) do-catch-finally
- D) try-catch-else

**Answer: B) try-except-finally**
**Explanation:** Python uses `try` block for code that might error, `except` to catch exceptions, and `finally` for cleanup code. (There is also an optional `else` block).

**Q10.** What is the result of attempting to use a mutable type (like a list) as a dictionary key?
- A) The dictionary accepts it normally.
- B) A TypeError is raised because keys must be hashable (immutable).
- C) A KeyError is raised.
- D) The list is implicitly converted to a tuple.

**Answer: B) A TypeError is raised because keys must be hashable (immutable).**
**Explanation:** Dictionary keys must be hashable. Mutable types like lists and dictionaries cannot be hashed because their contents can change.

---

## SECTION 4: SOFTWARE TESTING & STLC

**Q1.** What is the difference between Verification and Validation?
- A) Verification asks "Are we building the right product?", Validation asks "Are we building the product right?"
- B) Verification is dynamic testing, Validation is static testing.
- C) Verification asks "Are we building the product right?", Validation asks "Are we building the right product?"
- D) They are exactly the same concept.

**Answer: C) Verification asks "Are we building the product right?", Validation asks "Are we building the right product?"**
**Explanation:** Verification involves checking documents, design, and code (static). Validation involves executing the software to ensure it meets user needs (dynamic).

**Q2.** Which of the following best describes Smoke Testing?
- A) Exhaustive testing of all features.
- B) Testing to verify that a minor change hasn't broken existing functionality.
- C) A subset of test cases executed to verify that critical functionalities of a build are working.
- D) Testing done by the end-user.

**Answer: C) A subset of test cases executed to verify that critical functionalities of a build are working.**
**Explanation:** Smoke testing checks if the build is stable enough for further, rigorous testing.

**Q3.** What is Regression Testing?
- A) Retesting a specific bug to ensure it was fixed.
- B) Testing the software after code changes to ensure that existing functionalities have not been adversely affected.
- C) Testing the system in a production environment.
- D) Testing non-functional requirements like performance.

**Answer: B) Testing the software after code changes to ensure that existing functionalities have not been adversely affected.**
**Explanation:** Regression testing ensures new code changes didn't break existing working code. Retesting is checking a specific fixed bug.

**Q4.** A bug is found where a typo on the homepage doesn't affect functionality, but looks unprofessional. What is its likely Severity and Priority?
- A) High Severity, High Priority
- B) Low Severity, High Priority
- C) Low Severity, Low Priority
- D) High Severity, Low Priority

**Answer: B) Low Severity, High Priority (Often)**
**Explanation:** It doesn't crash the system (Low Severity), but since it's on the homepage where all users see it, business might want it fixed immediately (High Priority).

**Q5.** In Equivalence Partitioning for a field that accepts ages 18 to 65, which sets of test data are best?
- A) 17, 18, 65, 66
- B) 10, 30, 70
- C) 18, 30, 65
- D) 0, 18, 100

**Answer: B) 10, 30, 70**
**Explanation:** Equivalence partitioning divides data into valid and invalid partitions. 10 (invalid), 30 (valid), 70 (invalid) tests one from each partition.

**Q6.** Boundary Value Analysis for the same age field (18 to 65) would use which test values?
- A) 10, 30, 70
- B) 17, 18, 19, 64, 65, 66
- C) 18, 65
- D) 0, 18, 65, 100

**Answer: B) 17, 18, 19, 64, 65, 66**
**Explanation:** BVA tests the boundaries of equivalence partitions, specifically the exact boundary and just inside/outside it.

**Q7.** What does Defect Leakage mean?
- A) The number of defects found by QA divided by total test cases.
- B) Defects that escape the QA phase and are found by the customer in production.
- C) Defects introduced during the fixing of another defect.
- D) The number of defects found per line of code.

**Answer: B) Defects that escape the QA phase and are found by the customer in production.**
**Explanation:** Defect leakage = (Defects found in UAT/Prod) / (Defects found in QA + Defects found in UAT/Prod).

**Q8.** Which of the following is considered Black Box Testing?
- A) Unit testing
- B) Code coverage analysis
- C) System testing based on requirements without looking at code
- D) Static analysis

**Answer: C) System testing based on requirements without looking at code**
**Explanation:** Black box testing ignores the internal workings and focuses solely on inputs and outputs based on requirements.

**Q9.** What is the difference between a Test Plan and a Test Strategy?
- A) A test plan is project-specific, a test strategy is organization-wide.
- B) A test strategy is project-specific, a test plan is organization-wide.
- C) They are the exact same document.
- D) A test plan is written by developers, a test strategy by QA.

**Answer: A) A test plan is project-specific, a test strategy is organization-wide.**
**Explanation:** The Test Strategy is a static, high-level document defining testing approaches for the company. The Test Plan is derived from the strategy for a specific project.

**Q10.** What state does a bug transition to if the developer cannot reproduce it?
- A) Fixed
- B) Deferred
- C) Rejected / Not Reproducible
- D) Reopened

**Answer: C) Rejected / Not Reproducible**
**Explanation:** If the development team cannot replicate the steps to see the issue, they will mark it as Not Reproducible and send it back to QA.

**Q11.** What is White Box Testing?
- A) Testing the UI only.
- B) Testing with full knowledge of the internal code structure and logic.
- C) Testing performed by end users.
- D) Testing APIs.

**Answer: B) Testing with full knowledge of the internal code structure and logic.**
**Explanation:** In white-box testing, the tester writes test cases using knowledge of the internal code, branching, and logic flow (e.g., Unit Testing).

**Q12.** What is the difference between Agile and Waterfall testing?
- A) Waterfall has continuous testing, Agile tests only at the end.
- B) Agile tests continuously alongside development, Waterfall tests in a separate phase after development.
- C) Agile requires no documentation, Waterfall does.
- D) Waterfall is only for web apps, Agile is for mobile.

**Answer: B) Agile tests continuously alongside development, Waterfall tests in a separate phase after development.**
**Explanation:** Agile testing is iterative and continuous, while Waterfall is a sequential phase that only starts once all coding is complete.

**Q13.** What is a Test Scenario compared to a Test Case?
- A) A test scenario contains step-by-step instructions.
- B) A test scenario is a high-level description of what needs to be tested, while a test case contains specific steps, data, and expected results.
- C) A test scenario is written after a test case.
- D) They are identical.

**Answer: B) A test scenario is a high-level description of what needs to be tested, while a test case contains specific steps, data, and expected results.**
**Explanation:** Example Scenario: "Test Login functionality". Example Case: "Enter valid username 'admin', valid password '1234', click Login, verify redirection."

**Q14.** When would you use Decision Table Testing?
- A) When testing a loop.
- B) When system behavior depends on a combination of different input conditions.
- C) When testing database limits.
- D) When testing UI color schemes.

**Answer: B) When system behavior depends on a combination of different input conditions.**
**Explanation:** Decision tables capture complex business logic where multiple conditions result in specific actions.

**Q15.** What is Beta Testing?
- A) Testing performed by developers before committing code.
- B) Testing performed in a simulated environment by QA.
- C) Testing performed by real users in a real environment before official release.
- D) Testing API endpoints.

**Answer: C) Testing performed by real users in a real environment before official release.**
**Explanation:** Alpha testing is done internally. Beta testing is done by a select group of end-users outside the company.

---

## SECTION 5: AUTOMATION & SELENIUM

**Q1.** Which locator strategy is generally considered the fastest and most reliable in Selenium?
- A) XPath
- B) CSS Selector
- C) ID
- D) Tag Name

**Answer: C) ID**
**Explanation:** Locating by ID is the fastest because under the hood it calls the browser's native `document.getElementById()`, which is highly optimized.

**Q2.** What is an Explicit Wait in Selenium?
- A) A global wait applied to all elements for a certain amount of time.
- B) A wait that pauses the thread for a specific duration (Thread.sleep).
- C) A wait applied to a specific element to meet a certain condition (e.g., visibility, clickability) before proceeding.
- D) A wait that ignores all exceptions.

**Answer: C) A wait applied to a specific element to meet a certain condition (e.g., visibility, clickability) before proceeding.**
**Explanation:** Explicit waits (WebDriverWait) are dynamic and wait only as long as necessary for a specific condition, unlike implicit waits which are global.

**Q3.** What is the Page Object Model (POM)?
- A) A testing framework like TestNG.
- B) A design pattern where classes represent web pages, storing object locators and methods to interact with them.
- C) A method to execute tests in parallel.
- D) A tool for recording tests.

**Answer: B) A design pattern where classes represent web pages, storing object locators and methods to interact with them.**
**Explanation:** POM enhances test maintenance and reduces code duplication by separating test logic from page locators.

**Q4.** How do you switch to a different window or tab in Selenium?
- A) `driver.switch_to.window(window_handle)`
- B) `driver.change_window()`
- C) `driver.switch_tab()`
- D) `driver.navigate().to(new_tab)`

**Answer: A) `driver.switch_to.window(window_handle)`**
**Explanation:** You must retrieve the window handles using `driver.window_handles` and switch to the desired one using `driver.switch_to.window()`.

**Q5.** Which TestNG annotation runs exactly once before the entire test suite executes?
- A) @BeforeTest
- B) @BeforeClass
- C) @BeforeSuite
- D) @BeforeMethod

**Answer: C) @BeforeSuite**
**Explanation:** The execution hierarchy in TestNG is: Suite -> Test -> Class -> Method. @BeforeSuite runs first.

**Q6.** What is the difference between `driver.close()` and `driver.quit()`?
- A) `close()` shuts down the entire browser, `quit()` closes the current tab.
- B) `close()` closes the current window/tab having focus, `quit()` closes all windows/tabs and safely ends the WebDriver session.
- C) They do exactly the same thing.
- D) `quit()` is used only for mobile automation.

**Answer: B) `close()` closes the current window/tab having focus, `quit()` closes all windows/tabs and safely ends the WebDriver session.**
**Explanation:** Failing to call `quit()` can leave background browser processes running, consuming memory.

**Q7.** How do you handle a JavaScript Alert in Selenium?
- A) `driver.switch_to.alert.accept()`
- B) `driver.click_alert()`
- C) `driver.switch_to.frame().accept()`
- D) `driver.dismiss_alert()`

**Answer: A) `driver.switch_to.alert.accept()`**
**Explanation:** Alerts are not part of the DOM. You must switch context to the alert to `accept()`, `dismiss()`, or `send_keys()` to it.

**Q8.** What is Data-Driven Testing?
- A) Testing a database directly via SQL.
- B) Driving the execution of automated tests from an external data source (like Excel, CSV, or a Database).
- C) Generating random data for tests.
- D) Testing big data applications.

**Answer: B) Driving the execution of automated tests from an external data source (like Excel, CSV, or a Database).**
**Explanation:** In TestNG, this is typically achieved using the `@DataProvider` annotation.

**Q9.** Which class is used to simulate complex user interactions like drag-and-drop or hover in Selenium?
- A) Interaction class
- B) Actions class
- C) Mouse class
- D) Select class

**Answer: B) Actions class**
**Explanation:** The `Actions` class provides methods like `moveToElement()`, `dragAndDrop()`, `contextClick()`, and requires calling `.perform()` to execute.

**Q10.** What is Headless Browser Testing?
- A) Testing without asserting any results.
- B) Running browser tests without a graphical user interface (GUI).
- C) Testing an application that has no frontend.
- D) Using a browser that crashes frequently.

**Answer: B) Running browser tests without a graphical user interface (GUI).**
**Explanation:** Headless mode (like ChromeOptions `--headless`) is faster and uses fewer resources, making it ideal for CI/CD pipelines.

---

## SECTION 6: API TESTING & HTTP

**Q1.** Which HTTP method is considered idempotent and used to update an existing resource completely?
- A) POST
- B) PUT
- C) PATCH
- D) GET

**Answer: B) PUT**
**Explanation:** PUT updates a resource by replacing it entirely. It is idempotent (repeating it has the same effect). PATCH is for partial updates. POST creates a new resource and is NOT idempotent.

**Q2.** What does a 401 HTTP status code mean?
- A) Bad Request
- B) Unauthorized (Authentication required)
- C) Forbidden (Authenticated, but lacking permissions)
- D) Not Found

**Answer: B) Unauthorized (Authentication required)**
**Explanation:** 401 means the client must authenticate itself to get the requested response. 403 Forbidden means the client is known but doesn't have the right permissions.

**Q3.** What is the primary difference between REST and SOAP?
- A) REST uses XML exclusively, SOAP uses JSON.
- B) REST is a protocol, SOAP is an architectural style.
- C) SOAP is a protocol with strict standards (XML), REST is an architectural style that supports multiple formats (JSON, XML, HTML).
- D) REST is only for internal APIs.

**Answer: C) SOAP is a protocol with strict standards (XML), REST is an architectural style that supports multiple formats (JSON, XML, HTML).**
**Explanation:** REST is more lightweight and flexible, making it the standard for web APIs today.

**Q4.** Which header tells the server what type of data the client is sending in the request body?
- A) Accept
- B) Content-Type
- C) Authorization
- D) User-Agent

**Answer: B) Content-Type**
**Explanation:** `Content-Type` indicates the media type of the resource (e.g., `application/json`). The `Accept` header tells the server what type of data the client expects back.

**Q5.** What is an Idempotent API method?
- A) A method that returns different results every time it is called.
- B) A method that changes the server state only the first time it is called, and subsequent identical requests have no additional effect.
- C) A method that is used to delete data.
- D) A method that encrypts data.

**Answer: B) A method that changes the server state only the first time it is called, and subsequent identical requests have no additional effect.**
**Explanation:** GET, PUT, DELETE are idempotent. POST is not.

**Q6.** What does status code 502 signify?
- A) Internal Server Error
- B) Bad Gateway
- C) Service Unavailable
- D) Gateway Timeout

**Answer: B) Bad Gateway**
**Explanation:** 502 indicates that a server acting as a gateway or proxy received an invalid response from an upstream server. 500 is Internal Server Error.

**Q7.** In REST Assured, how do you validate the status code of a response?
- A) `.then().statusCode(200)`
- B) `.assertStatus(200)`
- C) `.check(200)`
- D) `.verify(200)`

**Answer: A) `.then().statusCode(200)`**
**Explanation:** REST Assured uses a BDD style format: `given()`, `when()`, `then()`. Status codes are validated in the `then()` block.

**Q8.** What is OAuth2?
- A) A hashing algorithm.
- B) A database connection protocol.
- C) An authorization framework that enables third-party applications to obtain limited access to a user's web service.
- D) A tool for parsing JSON.

**Answer: C) An authorization framework that enables third-party applications to obtain limited access to a user's web service.**
**Explanation:** OAuth2 uses tokens (like Bearer tokens) to grant access without sharing user passwords.

**Q9.** What is CORS?
- A) Cross-Origin Resource Sharing, a security feature that restricts web pages from making requests to a different domain.
- B) Central Object Relational System for databases.
- C) A type of HTTP method.
- D) An API testing framework.

**Answer: A) Cross-Origin Resource Sharing, a security feature that restricts web pages from making requests to a different domain.**
**Explanation:** Browsers enforce CORS to prevent malicious scripts on one origin from accessing sensitive data on another origin.

**Q10.** Which method is typically used to retrieve a specific record, such as a user with ID 5?
- A) GET /users
- B) GET /users/5
- C) POST /users/5
- D) PUT /users?id=5

**Answer: B) GET /users/5**
**Explanation:** In RESTful design, specific resources are accessed via the path parameters (e.g., `/resource/id`).

---

## SECTION 7: SQL

**Q1.** Which JOIN returns all records from the left table, and the matched records from the right table?
- A) INNER JOIN
- B) LEFT JOIN
- C) RIGHT JOIN
- D) FULL JOIN

**Answer: B) LEFT JOIN**
**Explanation:** A LEFT JOIN (or LEFT OUTER JOIN) ensures that all rows from the left table are returned, with NULLs in the right table's columns if there's no match.

**Q2.** What is the difference between WHERE and HAVING?
- A) They are interchangeable.
- B) WHERE is used to filter records before grouping, HAVING is used to filter records after aggregation/grouping.
- C) HAVING is used for string comparisons, WHERE for numbers.
- D) WHERE is used with JOINs, HAVING with Subqueries.

**Answer: B) WHERE is used to filter records before grouping, HAVING is used to filter records after aggregation/grouping.**
**Explanation:** You cannot use aggregate functions (like SUM, COUNT) in a WHERE clause; you must use HAVING after a GROUP BY.

**Q3.** What does the TRUNCATE command do?
- A) Deletes a table structure from the database.
- B) Deletes specific rows based on a WHERE clause.
- C) Deletes all rows from a table quickly, without logging individual row deletions, but keeps the table structure.
- D) Undoes the last transaction.

**Answer: C) Deletes all rows from a table quickly, without logging individual row deletions, but keeps the table structure.**
**Explanation:** TRUNCATE is a DDL command that resets the table. DELETE is a DML command that can use a WHERE clause and logs each deletion. DROP removes the table entirely.

**Q4.** Which normal form states that a table should not have partial dependencies on a composite primary key?
- A) 1NF
- B) 2NF
- C) 3NF
- D) BCNF

**Answer: B) 2NF**
**Explanation:** 1NF requires atomic values. 2NF requires 1NF and no partial dependencies. 3NF requires 2NF and no transitive dependencies.

**Q5.** What is a Primary Key?
- A) A column that speeds up searching.
- B) A column or set of columns that uniquely identifies each row in a table. It cannot be NULL.
- C) A column that links to another table.
- D) A column that must contain unique values, but can be NULL.

**Answer: B) A column or set of columns that uniquely identifies each row in a table. It cannot be NULL.**
**Explanation:** A UNIQUE constraint allows one NULL value, but a PRIMARY KEY does not allow any NULLs.

**Q6.** What is the difference between UNION and UNION ALL?
- A) UNION combines columns, UNION ALL combines rows.
- B) UNION returns only distinct rows, UNION ALL returns all rows including duplicates.
- C) UNION is faster than UNION ALL.
- D) There is no difference.

**Answer: B) UNION returns only distinct rows, UNION ALL returns all rows including duplicates.**
**Explanation:** Because UNION performs a distinct sort operation to remove duplicates, UNION ALL is significantly faster.

**Q7.** Which aggregate function returns the total number of rows in a table, including those with NULL values?
- A) SUM()
- B) COUNT(column_name)
- C) COUNT(*)
- D) TOTAL()

**Answer: C) COUNT(*)**
**Explanation:** `COUNT(*)` counts rows. `COUNT(column_name)` counts only non-NULL values in that specific column.

**Q8.** What is an Index in SQL used for?
- A) To encrypt data.
- B) To enforce foreign key constraints.
- C) To speed up the retrieval of records from a database table.
- D) To automatically increment primary keys.

**Answer: C) To speed up the retrieval of records from a database table.**
**Explanation:** Indexes work like the index of a book, allowing the database engine to find data faster than a full table scan. However, they slow down INSERTs and UPDATEs.

**Q9.** A Subquery can be used in which of the following clauses?
- A) SELECT
- B) FROM
- C) WHERE
- D) All of the above

**Answer: D) All of the above**
**Explanation:** Subqueries (inner queries) can be nested inside SELECT, INSERT, UPDATE, or DELETE statements, or inside another subquery.

**Q10.** What happens when you use an INNER JOIN without a joining condition?
- A) It returns an error.
- B) It behaves like a LEFT JOIN.
- C) It produces a Cartesian product (Cross Join) of the two tables.
- D) It returns no rows.

**Answer: C) It produces a Cartesian product (Cross Join) of the two tables.**
**Explanation:** Without an ON clause, every row in the first table is joined with every row in the second table.

---

## SECTION 8: GIT & CI/CD

**Q1.** What is the primary difference between `git merge` and `git rebase`?
- A) Merge creates a new commit preserving history, rebase rewrites project history by placing your commits at the tip of the branch.
- B) Merge deletes the source branch, rebase keeps it.
- C) Rebase is only used for remote repositories.
- D) Merge is for text files, rebase is for binary files.

**Answer: A) Merge creates a new commit preserving history, rebase rewrites project history by placing your commits at the tip of the branch.**
**Explanation:** Rebasing creates a cleaner, linear history but should not be used on public branches because it rewrites history.

**Q2.** What command saves your local modifications temporarily without committing them?
- A) git save
- B) git pause
- C) git stash
- D) git hold

**Answer: C) git stash**
**Explanation:** `git stash` temporarily shelves changes you've made to your working directory so you can work on something else, and then apply them back later.

**Q3.** What does Continuous Integration (CI) primarily involve?
- A) Automatically deploying code to production.
- B) Developers frequently merging their code changes into a central repository, followed by automated builds and tests.
- C) Manual testing of the application.
- D) Writing unit tests.

**Answer: B) Developers frequently merging their code changes into a central repository, followed by automated builds and tests.**
**Explanation:** CI ensures that the main branch is always in a working state by running automated checks on every commit.

**Q4.** What is the purpose of a Dockerfile?
- A) It stores database credentials.
- B) It contains instructions to build a Docker image.
- C) It is a log file for Docker containers.
- D) It manages multiple Docker containers simultaneously.

**Answer: B) It contains instructions to build a Docker image.**
**Explanation:** A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.

**Q5.** In Jenkins, what is a Pipeline?
- A) A suite of plugins that supports implementing and integrating continuous delivery pipelines.
- B) A connection to a database.
- C) A tool for managing git branches.
- D) A physical cable connecting servers.

**Answer: A) A suite of plugins that supports implementing and integrating continuous delivery pipelines.**
**Explanation:** Jenkins Pipeline allows you to define your entire build process, which typically includes stages for building an application, testing it and then delivering it.

**Q6.** What does `git cherry-pick` do?
- A) Deletes a specific commit.
- B) Applies the changes introduced by a specific existing commit to the current branch.
- C) Selects the best code from a pull request.
- D) Reverts the last commit.

**Answer: B) Applies the changes introduced by a specific existing commit to the current branch.**
**Explanation:** Useful if you need a specific hotfix from one branch into another without merging the entire branch.

**Q7.** What is the difference between Continuous Delivery (CD) and Continuous Deployment (CD)?
- A) They are the exact same thing.
- B) Delivery requires manual approval to release to production; Deployment releases to production automatically.
- C) Delivery is automated, Deployment is manual.
- D) Delivery is for frontend, Deployment is for backend.

**Answer: B) Delivery requires manual approval to release to production; Deployment releases to production automatically.**
**Explanation:** In Continuous Deployment, every change that passes all stages of the production pipeline is released to customers without human intervention.

**Q8.** How do you resolve a Git merge conflict?
- A) Run `git resolve`.
- B) Delete the repository and clone again.
- C) Edit the conflicted files manually, remove the conflict markers, add the files, and commit.
- D) Git always resolves them automatically.

**Answer: C) Edit the conflicted files manually, remove the conflict markers, add the files, and commit.**
**Explanation:** When Git cannot automatically merge changes (e.g., both branches edited the same line), it pauses and asks the developer to manually choose which changes to keep.

**Q9.** In the GitFlow branching strategy, what is the purpose of the `release` branch?
- A) It is the main production branch.
- B) It is used to develop new features.
- C) It is used for preparation and testing of a new production release, allowing for minor bug fixes before merging into main.
- D) It is used for hotfixes.

**Answer: C) It is used for preparation and testing of a new production release, allowing for minor bug fixes before merging into main.**
**Explanation:** The `main` (or `master`) branch holds production code, `develop` holds the latest delivered development changes. `release` branches branch off from `develop`.

**Q10.** Which Jenkins trigger will build a project whenever changes are pushed to a Git repository?
- A) Build periodically (Cron)
- B) Poll SCM
- C) GitHub hook trigger for GITScm polling
- D) Build after other projects are built

**Answer: C) GitHub hook trigger for GITScm polling**
**Explanation:** Using Webhooks is the most efficient way to trigger builds instantly on a push, whereas "Poll SCM" constantly asks the repository if there are changes.

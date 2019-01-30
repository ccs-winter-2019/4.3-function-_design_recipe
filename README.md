# Function Design Recipe

The idea of a "design recipe" for programs comes from the Program By Design curriculum.

http://www.htdp.org/2018-01-06/Book/part_one.html#%28part._sec~3afuncs%29

1. What's the input and where does it come from? Does it come as arguments? Does it read data from what the user has entered? Does it come from a mouse click or other DOM event? Does it come from the server?
```
  var name = $('.js-name').val();

  $('.js-profile-form').on('submit', saveProfile);
```
2. What's the output and where does it go? Is it returned from the function? Is it printed? Does it send the results to a server?
  * Deciding whether to design functions with parameters and returned values or alternatively with print statements or other direct interactions is a question that requires a lot of thought.
  * As a general principle, though, it's usually best to write every function you can with parameters and return values. That makes them flexible; the program that calls it can decide what to do with the returned result (print it, send it to a server, whatever).

3. Write a one-line purpose statement or description that says in simple English what the function does.
```
  // Calculate the square of a number
```
4. Write a type contract that states the function's name and the names and types of its parameters and return value.

```
  // function description
  // parameter description
  // return description
  
  function name(parameter) {
  
  }
```
```
  // Calculate the square of a number
  // num is a Number to square
  // returns the square
  
  function square(num) {
  
  }
```

5. Write some examples of calling the function, including the results you expect in each case.
  * For functions that return values, use console.assert which expects a Boolean (true or false) expression that should be true if the function is correct:
```
  console.assert(square(2) == 4);

  console.assert(square(-1) == 1);
```
  * Write enough different examples to convince yourself that your function works correctly on all expected kinds of data.

6. Write the body of the function.
```
  // Calculate the square of a number
  // num is a Number to square
  // returns the square

  function square(num) {
    return Math.pow(num, 2);
  }

  console.assert(square(2) == 4);

  console.assert(square(-1) == 1, 'custom message here');
```
7. Run the function and check the results.
  * If the assertions are true, everything stays quiet; if one is false, you get an error message that helps you locate the source of the problem
  * Resolve any discrepancies and repeat the process until all the tests pass

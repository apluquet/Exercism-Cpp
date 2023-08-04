# Tests

Running the tests involves running `cmake -G` and then using the build command appropriate for your platform.
Detailed instructions on how to do this can be found on the [Running the Tests][cpp-tests-instructions] page for C++ on exercism.org.

## Passing the Tests

Get the first test passing, following the [three rules of test-driven
development (TDD)][three-laws-of-tdd].
Start to create just enough structure by declaring namespaces, functions, lasses, etc., to satisfy all (and only) compiler errors, and get the test to run and fail.
Then, write just enough code to get the test to pass.
Once you've done that, you can activate the next test.

To do so, go to the `<exercise>_test.h` file. You will find this line, after the first test :

```C++
#if defined(EXERCISM_RUN_ALL_TESTS)
```

This is a [preprocessor directive][preprocessor-doc].
All the tests between this line and the `#endif` instruction (at the end of the file in our case), which closes this directive, will be ignored.
To make following test available, move down the line `#if defined (EXERCISM_RUN_ALL_TESTS)` of one test.

This may result in compile errors as new constructs may be invoked that you haven't yet declared or defined.
Again, fix the compile errors minimally to get a failing test, then change the code minimally to pass the test, refactor your implementation for readability and expressiveness and then go on to the next test.

Try to use standard C++17 facilities in preference to writing your own low-level algorithms or facilities by hand.

[cpp-tests-instructions]: https://exercism.org/docs/tracks/cpp/tests
[three-laws-of-tdd]: http://butunclebob.com/ArticleS.UncleBob.TheThreeRulesOfTdd
[preprocessor-doc]: https://cplusplus.com/doc/tutorial/preprocessor/

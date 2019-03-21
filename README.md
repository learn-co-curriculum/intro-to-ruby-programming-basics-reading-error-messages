# Reading Ruby Error Messages

## Learning Goals

- Read the three different parts of an error message.
- Identify four error types- name errors, syntax errors, type errors, and
  division errors- and fix them
- Describe a test suite, where it's found in a lab, and its purpose
- Use the `learn` command in terminal to run the tests and read errors for this
  lab.

## Introduction

In this lab, we will be going over common error messages, types of errors and
how to approach resolving them. The errors you are tasked with resolving are
present in the four files within the `lib` folder. As you read and resolve these
errors, run `learn` to confirm your success.

## Reading Error Messages

To start, we're going to run a Ruby file with our first error. In your terminal,
run `ruby lib/a_name_error.rb`. You should see something close to the following:

```
Traceback (most recent call last):
lib/a_name_error.rb:3:in `<main>': undefined local variable or method `hello_world' for main:Object (NameError)
```

Error messages have 3 parts that we can use to help identify and fix the issue.

#### Error Location

The first part of the error is the location, where the error occurred:

```
lib/a_name_error.rb:3:in `<main>':
```

- `lib/a_name_error.rb` is the file the error occurred in
- `3` is the line of code with the error
- `<main>` is the scope of the error

With the file and the exact line of code, we now know where to go in order to
work on implementing a fix for this error.

#### Error Description

The second part of the error is the description, the _cause_ of the error:

```
undefined local variable or method `hello_world' for main:Object
```

The interpreter does the best job it can to tell you what it thinks went wrong.
In this case, it is saying it encountered `hello_world`, which is currently
undefined.

#### Error Type

At the end of the error message, we see the error type:

```
(NameError)
```

This is a [Ruby Error Type](http://www.ruby-doc.org/core-2.2.0/Exception.html).
This, combined with the description, can often give us a clearer idea of what
went wrong.

## Four Common Error Types

### Name Errors

Name errors are caused when a given name is invalid or undefined. Whenever the
Ruby interpreter encounters a word it doesn't recognize, it assumes that word is
the name of a variable or a method. If that word was never defined as either a
variable or a method, it will result in a name error.

```
lib/a_name_error.rb:3:in `<main>': undefined local variable or method `hello_world' for main:Object (NameError)
```

To resolve name errors, take a look at the word causing the error as well as the
code around it. Is this word supposed to be defined somewhere earlier? Can we
give it a definition to fix the problem? Or, alternatively, do we need it at
all? Maybe we can just delete it!

Fix the name error present in `lib/a_name_error.rb` before continuing. Run
`learn` to confirm you were successful. If you've solved the error, you should
see the following at the top of your test results:

```
Error tests
  NameError
    raises a NameError when encountering undefined barewords
  SyntaxError
    raises a SyntaxError for nonsensical code (FAILED - 1)
```

On to the second test and error type, syntax errors!

### Syntax Errors

Syntax errors are pretty self-explanatory: they're the result of incorrect
syntax. Something is missing, out of place, or extra in our code.

Run `ruby lib/a_syntax_error.erb` in your terminal. You'll see the following:

```
lib/a_syntax_error.rb:3: syntax error, unexpected end-of-input
```

Here, Ruby is saying that on line 3, things ended unexpectedly. This suggests
a piece of code is missing.

Fix the name error present in `lib/a_syntax_error.rb` before continuing. Run
`learn` to confirm you were successful. If you've solved the error, you should
now see the following at the top of your test results:

```
Error tests
  NameError
    raises a NameError when encountering undefined barewords
  SyntaxError
    raises a SyntaxError for nonsensical code
  TypeError
    raises a TypeError for objects of the wrong type (FAILED - 1)
```

Two errors resolved, two to go. Next are type errors.

### Type Errors

When you try and do a mathematical operation on two objects of a different type,
you will receive a _type_ error. For example, if you try and add a string to an
integer, Ruby will complain:

```ruby
1 + "1"
```

...produces the following error:

```
String can't be coerced into Integer (TypeError)
```

Running `ruby lib/a_type_error.rb` produces a similar error. Fix this error
before continuing. Run `learn` to confirm you were successful. If you've solved
the error, you should now see the following at the top of your test results:

```
Error tests
  NameError
    raises a NameError when encountering undefined barewords
  SyntaxError
    raises a SyntaxError for nonsensical code
  TypeError
    raises a TypeError for objects of the wrong type
  ZeroDivisionError
    raises a ZeroDivisionError for dividing by zero (FAILED - 1)
```

Next up, division errors!

### Division Errors

Division errors are caused when a given number is divided by 0.

In `lib/a_division_by_zero_error.rb`, there are _two_ division errors. Running
`ruby lib/a_division_by_zero_error.rb` produces:

```
lib/a_division_by_zero_error.rb:3:in `/': divided by 0 (ZeroDivisionError)
```

Fix the two division errors to pass the final test. Run `learn` to confirm your
success. You should see 4 examples, 0 failures.

```
Error tests
  NameError
    raises a NameError when encountering undefined barewords
  SyntaxError
    raises a SyntaxError for nonsensical code
  TypeError
    raises a TypeError for objects of the wrong type
  ZeroDivisionError
    raises a ZeroDivisionError for dividing by zero

Finished in 0.01457 seconds (files took 0.2058 seconds to load)
4 examples, 0 failures
```

Run `learn submit` to submit your work before continuing to the next lesson.

## Troubleshooting

If at any point, you are having trouble with this lesson or are unable to pass
all the tests, watch the [video][video] linked in the Resources section below.

## Conclusion

Like playing a game of Clue, we can use the information provided from an error
message, along with a bit of experimenting, to find and resolve a problem. This
is one of the best parts of programming: debugging and fixing errors! It's like
you're a detective solving a crime. The only bad thing is that more often than
not, you're also the criminal that caused the error in the first place.

Errors are clues, and reading them is the interpreter telling you what to do to
fix the program and move on.

## Resources

- [Reading Error Messages Video][video]
- [NameErrors][nameerror]
- [TypeErrors][typeerror]

[video]: https://www.youtube.com/embed/L_eoziYKLXw?rel=0&showinfo=0
[aws video]: http://flatiron-videos.s3.amazonaws.com/ironboard/ruby/ruby-lecture-reading-error-messages/ruby-lecture-reading-error-messages.mp4
[nameerror]: http://ruby-doc.org/core-2.5.0/NameError.html
[typeerror]: http://ruby-doc.org/core-2.5.0/TypeError.html

<p class='util--hide'>View <a href='https://learn.co/lessons/ruby-lecture-reading-error-messages'>Reading Error Messages</a> on Learn.co and start learning to code for free.</p>

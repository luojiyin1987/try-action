> -  原文地址：[Python split() – String Splitting Example](https://www.freecodecamp.org/news/python-split-string-splitting-example/)
> -  原文作者：[Ihechikara Vincent Abba](https://www.freecodecamp.org/news/author/ihechikara/)
> -  译者：
> -  校对者：

![Python split() – String Splitting Example](https://www.freecodecamp.org/news/content/images/size/w2000/2022/05/tania-melnyczuk-eIY9QaolhLg-unsplash--3-.jpg)

The `split()` method in Python splits characters in a string into separate items in a list.

In this tutorial, we'll go over some examples to help you learn how to use the `split()` method. We'll start from the syntax and then see how we can modify the list returned using the `split()` method's parameters.

## Syntax of the `split()` Method in Python

The `split()` method takes in two parameters. Here's what the syntax looks like:

```python
str.split(separator, maxsplit)
```

The parameters above are `separator` and `maxsplit`. These parameters are both optional, but let's discuss what they do.

`separator` specifies the character at which the split occurs. If not specified, whitespaces will be used as the default character where splitting occurs. You'll understand this better in the examples in the coming sections.

`maxsplit` specifies the maximum number of splits. The default value is -1 which allows for a continuous number of splits. This argument is also optional.

## How to Use the `split()` Method Without Parameters

In this section, we'll see some examples of string splitting using the `split()` method without passing in any parameters.

```python
myString = "Python is a programming language"

print(myString.split())

# ['Python', 'is', 'a', 'programming', 'language']
```

In the code above, we created a string called `myString` with five characters making up the string: "Python is a programming language".

We then used the `split()` method on our string using dot notation.

When printed to the console, each character in the string became a separate item in a list data type: `['Python', 'is', 'a', 'programming', 'language']`.

The `split()` method is able to separate each word because, by default, whitespaces indicate the point of splitting for each character (refer to the `separator` parameter in the previous section).

## How to Use the `split()` Method With Parameters

In this section, we'll understand how to use the `split()` method's parameters with examples.

```python
myString = "Hello World!, if you're reading this, you're awesome"

print(myString.split(", "))

# ['Hello World!', "if you're reading this", "you're awesome"]
```

In the example above, we passed in a comma (,) as the `separator`: `myString.split(", ")`.

So instead of splitting the characters after each whitespace, the characters will only be split when a comma appears: `['Hello World!', "if you're reading this", "you're awesome"]`. This means that characters that appear before a comma will be grouped together.

In the next example, we'll work with the second parameter – `maxsplit`.

```
myString = "Hello World!, if you're reading this, you're awesome"

print(myString.split(", ", 0))

# ["Hello World!, if you're reading this, you're awesome"]
```

We've added a `maxsplit` value of 0 in the code above. This controls how the string is split. 0 implies 1 so the characters are returned as one item in a list:  `["Hello World!, if you're reading this, you're awesome"]`

Let's change the number and see what happens

```python
myString = "Hello World!, if you're reading this, you're awesome"

print(myString.split(", ", 1))

# ['Hello World!', "if you're reading this, you're awesome"]
```

Now that we've changed the number to 1, the characters are split into two items in the list – ''Hello World!'' and "if you're reading this, you're awesome".

Omitting the `maxsplit` value will set it to -1  by default. This negative value allows the `split()` methods to split each character continuously into separate items until there are no more characters left. If there is a specified `separator`, the splitting will be done with respect to that value – otherwise, whitespaces will be used.

## Conclusion

In this article, we talked about the `split()` method in Python which splits characters in a string and returns them as items in a list.

We saw the syntax for the `split()` method and the two parameters provided by default – the `separator` and `maxsplit` parameters.

We also saw some examples divided into two sections. The first section showed how to use the `split()` method without parameters while the second showed how we'd use the method's parameters to achieve varying results.

Happy coding!

## Development Pancake Challenge

### The Challenge

We want to see a full-stack application with a simple one-page angular frontend and an API that uses AWS API gateway with a python lambda function.

### The API

Please create a REST API through which you invoke a Lambda function using an HTTP request that will run in the AWS environment. Your Lambda function will accept an array of strings and calculate if each string is a palindrome.

A string is a palindrome that reads the same backward or forward.

[Merriam Webster dictionary explanation](https://www.merriam-webster.com/dictionary/palindrome)

Your API should expect an array of strings
```
[
"racecar",
"A man, a plan, a canal: Panama.",
"A test"
]
```

Your API response should have an array of objects as json. Each item should contain

-   `text` `string`: The text that was provided in the request
-   `is_pure_palindrome` `boolean`: if the text is a palindrome without stripping spaces and special characters e.g., `racecar`, as the word racecar reads the same when you read backward without removing spaces or special chars.
-   `is_palindrome` `boolean`: if the text is a palindrome when you remove all the spaces and special chars. e.g., `A man, a plan, a canal: Panama.` as it reads the same when you remove spaces and special characters

Sample response
```
[
  {
    "text": "racecar",
    "is_pure_palindrome": true,
    "is_palindrome": true
  },
  {
    "text": "A man, a plan, a canal: Panama.",
    "is_pure_palindrome": false,
    "is_palindrome": true
  },
  {
    "text": "A test",
    "is_pure_palindrome": false,
    "is_palindrome": false
  }
]
```

For the API Gatewan and Lambda implementation details on AWS [https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway-tutorial.html](https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway-tutorial.html)

### The UI

We want to see an Angular SPA (single-page application) that will have one page with a table that will list the strings and boolean values that return from your API

-   You should insert the attached test-strings.ts file and send the strings in the file to your API
-   The API should accept the strings and calculate is_pure_palindrome and is_palindrome for each string
-   The API should return an array of objects as JSON
-   The UI should get the API response and show it in a table
-   The UI should highlight the pure palindrome rows (if is_pure_palindrome = true for the row data) with green
-   The UI should highlight the palindrome but not pure palindrome rows with yellow

-   (if is_pure_palindrome = true and is_palindrome = false)

-   The UI shouldn't highlight the rows if the text is not a palindrome

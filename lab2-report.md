<!--
  Lab Report 2 for CSE 15L
  Winter 2023 Quarter
-->

# Lab Report 2
### Jefferson Umanzor

---

### `ChatServer.java` Code
![Code](images/lab2.png)

## Messages Query Showcase

*Screenshot 1*

![Message One](images/message-1.png)
- In this screenshot, I entered the URL: `http://localhost:2024/add-message?s=This is my first message!&user=Jefferson`.
- The `handleRequest` method then runs and takes the URL as an argument. The method encounters an `if statement` that calls the `getPath()` method and the String class' `equals()` method to determine whether the URL's path is empty.
- The following `else if` statement calls the `getPath()` method and the String class' `equals()` method to obtain the current path and then calls the String class' `contains()` method with the path `"/add-message"` to determine if the proper path was passed.
- The URL query is then split using the String class' `equals()` method, utilizing the `=` argument. It is held within the String array `parameters`, separating the query received from `getQuery()` into `[s, <string>&user, <string>]`.
- The String class' `equals()` method is called once more to determine if `parameters[0]` is equal to `s`. If so, `parameters[1]`, `[<string>&user]`, is split using the String class' `equals()` method with the argument `&`. Thus, the String array `obtain_message` holds `[<string>, user]`.
- The outputted message is then added to the ArrayList `messages_list`, which contains all the messages, using the ArrayList class' `add()` method with the message passed as an argument. The message is derived using the String class' `format()` method, taking `parameters[2]`, the User, and `obtain_message[0]`, the message, as arguments, formatting them in the form `"%s: %s\n"`.
- A String named `printed_output` is then created and runs through a `for loop` to concatenate each String, or `stored_message`, held within `messages_list`.
- Lastly, the printed output is returned using the String class' `format()` method, with the argument `printed_output`, formatting the message as `%s`.

*Screenshot 2*

![Message Two](images/message-2.png)
- In this screenshot, I entered the URL: `http://localhost:2024/add-message?s=Here is a second message.&user=Person`.
- The `handleRequest` method then runs and takes the URL as an argument. The method encounters an `if statement` that calls the `getPath()` method and the String class' `equals()` method to determine whether the URL's path is empty.
- The following `else if` statement calls the `getPath()` method and the String class' `equals()` method to obtain the current path and then calls the String class' `contains()` method with the path `"/add-message"` to determine if the proper path was passed.
- The URL query is then split using the String class' `equals()` method, utilizing the `=` argument. It is held within the String array `parameters`, separating the query received from `getQuery()` into `[s, <string>&user, <string>]`.
- The String class' `equals()` method is called once more to determine if `parameters[0]` is equal to `s`. If so, `parameters[1]`, `[<string>&user]`, is split using the String class' `equals()` method with the argument `&`. Thus, the String array `obtain_message` holds `[<string>, user]`.
- The outputted message is then added to the ArrayList `messages_list`, which contains all the messages, using the ArrayList class' `add()` method with the message passed as an argument. The message is derived using the String class' `format()` method, taking `parameters[2]`, the User, and `obtain_message[0]`, the message, as arguments, formatting them in the form `"%s: %s\n"`.
- A String named `printed_output` is then created and runs through a `for loop` to concatenate each String, or `stored_message`, held within `messages_list`.
- Lastly, the printed output is returned using the String class' `format()` method, with the argument `printed_output`, formatting the message as `%s`.

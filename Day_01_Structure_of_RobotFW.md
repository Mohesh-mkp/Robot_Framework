### Structure of Robot Framework
It consists of mainly 4 blocks
1. Settings
2. Variable
3. Test Case
4. Keyword

And these are noted by __***__ preceding and following the block names

### 1. Settings:   
In this block, all the resource libraries are going to import or store the relevant libraries by adding their source to it.
```robot

*** Settings ***
Library    SeleniumLibrary
Library    Mouse

```
### 2. Variables:
In this block, we are going to address the variables.   
There are different types of variable notation. If we want to create a simple variable to store value we assign the variable with __'$'__ notation, whereas for list it's __'@'__ and for dictionary it is __'&'__.   
```robot
*** Variables ***
${name}    John Doe
${age}     30
${is_adult}    ${True}

@{fruits_list}    Apple    Banana    Orange

&{person_dict}    name=John Doe    age=30    is_adult=${True}

```

### 3. Test Cases:
In this block, we are going to write a test case.
```robot
*** Test Cases ***
Web Test
    Open Browser    https://example.com    chrome
    Input Text    search_box    Robot Framework
    Click Button    search_button
    Close Browser
```
### 4. Keyword:
In this block, we are going to write a block of code or a block of statements that will execute the part of the keyword.
```robot
*** Settings ***
Variables  login_variables.robot

*** Test Cases ***
Login With Valid Credentials
    [Template]  Login Test
    Login Test  ${valid_username_1}  ${valid_password_1}
    Login Test  ${valid_username_2}  ${valid_password_2}
    Login Test  ${valid_username_3}  ${valid_password_3}

*** Keywords ***
Login Test
    [Arguments]  ${username}  ${password}
    Log  Trying to log in with username: ${username} and password: ${password}
    # Add your actual login steps here
    Should Be True  Login Successful?  # Assuming a keyword for checking successful login
```



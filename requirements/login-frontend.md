# Login workflow

## Steps
* 1. Startup screen with welcome from [figma](https://www.figma.com/design/VTincafF2dFoPM7zhZq5KH/Simple-Login-%E2%9C%A8--Community-?node-id=92-209&t=4R7Lv1FULc7HSmbi-4)

* 2. Login screen with email and password fields, and a login button from [figma](https://www.figma.com/design/VTincafF2dFoPM7zhZq5KH/Simple-Login-%E2%9C%A8--Community-?node-id=92-610&t=4R7Lv1FULc7HSmbi-4)

## Input validation
* Email field should validate that the input is a valid email address format
* Password field should validate that the input is at least 8 characters long

## Error handling
* If the email or password is incorrect, display an error message to the user
* If there is a network error during login, display a network error message to the user

## Success handling
* If the login is successful, navigate the user to the main dashboard screen

## Call Login API
* The login screen should call the login API endpoint with the email and password when the user clicks the login button
* The API response should be handled appropriately, displaying success or error messages as needed

API Specification
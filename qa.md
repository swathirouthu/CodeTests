# SignalPath, LLC.
## QA Engineer Code Assessment

1. SignalPath has bought a new vending machine and it is going to be under heavy usage (we love snacks). You have been nominated to test it and make sure it is up to the task. How would you approach this?

      To begin with, my steps would be
      - Identify the end users by discussing with People responsible for purchasing the vending machine(is it only for employees or vistors as well)
      - Identify the size, location, environment and Flooring the vending machine is going to   reside on
      - Identify if the snacks are going to be paid or free
      - Identify if the Vending Machine going to hold only snacks or beverages as well?
      - Determine if the Vending machine accept both cash and Credit cards

      After getting as much information from everyone who were involved in approving the purchase, i would review the documentation which came along with the vending machine. This should provide additional information to some of the questions above.

      For this exercise, based on the information provided, i am going to make the following assumptions - 
      This is a normal vending machine for vending snacks
      There will be no Soda/Coffee vending
      The vending machine will accept only $1, $5 and all coins except pennies. Change is given back in the form of coins
      There will be enough snacks for all employees


      Test cases:

      - Verify if the vending machine is placed in an location deemed safe according to the guidleines provided in the documentation.
      - Verify the location of Vending machine is accessible to all employees and visitors
      - Verify the vending machine is plugged into a three-prong electrical outlet
      - Verify if the Vending machine is turned on after plugged into an outlet. 
      - Verify if there is a switch to turn on and off the vending machine
      - Verify there is enough space to open the door to stock and restock snacks
      - Verify all the snacks fit into the spiral coils cleanly inside the machine
      - Verify all the snack rows are labeled clearly with price to be input the code 
      - Verify the electronic display shows the default message to insert money above the buttons to input the code
      - Verify the buttons are numbered 0 - 9 and letters and a clear option
      - Verify the machine can accept bills in the correct direction and coins
      - Verify the bills are rejected if inserted incorrectly
      - Verify invalid coins are rejected through the change slot
      - Verify behavior if the keys are pressed without inserting any money
      - Verify after the right money is inserted, and the snack label entered, snack is dispensed through the snack hole
      - Verify pressing an incorrect label, does not dispense any snacks
      - Verify pressing multiple labels after inserting money for one snack does not dispense multiple snacks
      - Verify change is dispensed correctly if excessive money inserted (for example, if $1 inserted and snack costs 75c, 25c should be dispensed)
      - Verify behavior, if money inserted, but no selection made for some time, are the bills/coins given back? If yes, timeframe
      - Verify behavior if no change is available in vending machine
      - Verify behvaior of Vending machine if snacks are improperly stuffed in tray
      - Verify the speed of the snack dispensed (is it too slow or too fast)
      _ verify shaking the machine vigoroulsy does not throw out any snacks
      - Verify proper warning label is displayed on the machine, in case snacks in vending machine have any allergy causing ingredients (like peanuts)

2. Create two test cases for Twitter’s authentication functionality.

      Assumptions : Browser Testing
      Preconditions: Navigate to http://www.twitter.com. 
      Twitter website should be opened with Sign up and Log in options displayed. Click on "Log in"

      Test Cases:

      Enter a a valid 'Phone/email/username' in the first field and the corresponding 'Password' and hit Log in. 
      User should be redirected to https://twitter.com/home with "Home" shown above the "what's happening" field to tweet. Username should be seen on the bottom
      left of the page. 

      Enter an invalid 'Phone/email/username' and 'Password' combination. User is not logged and a message shown 
      "The username and password you entered did not match our records. Please double-check and try again."
    

3. Using any tool of your choice, create an automated test for one of the two test cases from the previous question (Twitter); or if your scripting knowledge is limited, discuss how you would go about testing the test case using automation.

     Using Selenim Webdriver and Java, the code would be the following:
     
    //Import all the selenium webdriver libraries
    //Import chrome driver library

    //Initialize a class with a main method

    //Commands inside a class

    System.setProperty("webdriver.chrome.driver", "Path of the chrome driver");
    ebDriver driver=new ChromeDriver();
    driver.manage.window.maximize();
    driver.get("https://www.twitter.com/login");
    WebElement u = driver.findElement(By.id("Get the ID property by inspecting element of username field")); 
    //in case id not available, class or xpath can be used
    u.clear();
    u.sendkeys("Enter Emailaddress or phone number or username")
    WebElement p = driver.findElement(By.id("Get the ID property by inspecting element of password field")); 
    //in case id not available, class or xpath can be used
    p.clear();
    p.sendkeys("Enter Password here")
    WebElement c = driver.findElement(By.id("Get the ID property by inspecting element of Log in field")); 
    //in case id not available, class or xpath can be used as a property
    c.click();

    To verify user is logged in, we can validate the url after logging in as below
    String actualUrl="https://twitter.com/home";
    String expectedUrl= driver.getCurrentUrl();
    Assert.assertEquals(actualUrl, expectedUrl);

    Test Case 1 : After the script is run, Test is passed if the actual URL (which is for a valid login) matches the expected URL
    (based on the User's current login state)

    Test Case 2 : If the actual URL does not match the expected URL, test is failed
     

4. Suppose you have a web site with two form elements on it: a multi-line textarea and button that says “multiply”. The expected behavior is that when you click “multiply” all of the numbers written in the textarea are multiplied together and written next to the textarea. For instance, if the textarea has the numbers 5, 7, 11 then the output will be 385. Identify all the test cases that you would need to write. (You do not actually need to write the detailed steps for every test case, just the summary.)

    In Summary, the test cases would cover both Positive and negavtive testing, boundary value analysis.
    Check the max character limits of the fields
    Check to see if the fields accept any alphabets including special characters like decimals other than numbers
    Can the text area display the full output in case of large numbers
    Is multiplying with 0 display the output as 0
    Does multiply functionality work if some text areas are left empty and only one text area is filled in
    verify behavior if "multiply" is pressed without entering any numbers
    Can you used tab to move from field to field and to 'multiply' 
    Testing 'multiply' with the largest numbers possible in all the fields
    Verifying results with the same numbers (including 0) in all fields
    Verify on different browsers (browser compatibility)
    Able to Clear out the fields to enter new numbers
    Clicking on Multiple again and again with same numbers should produce the same result
    Verify if able to copy numbers and paste in other text areas
    Verify results are accurate by verifying against a calculator in all cases
    
    
    
    

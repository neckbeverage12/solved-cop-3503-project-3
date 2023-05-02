Download Link: https://assignmentchef.com/product/solved-cop-3503-project-3
<br>
Details

In this project, your chatbot will be given functionality that makes it talk back to you and respond to keywords it finds in the user's sentences.

&nbsp;

Objective

This time around your program will take input from the user and give it to your ChatBot. The chatbot will look through your message, find any specific keyword, and print out a response based on the keyword it finds. It will only respond to two keywords a at a time at max--no more.

&nbsp;

Instructions

As you will be reusing code from project three, you should be starting this project with the following three classes created and partially implemented:

Main.java (class name Main)
ChatBot.java (class name ChatBot)
Memory.java (class name Memory)
Conversion.java (class named Conversion)

In quick review, the Memory class contains variables that represent important information that a ChatBot would need to know. The ChatBot class contains logic for how a ChatBot can respond to a user (with various 'reply' functions). The ChatBot class has a memory object as an instance variable. Main was originally used to create a single ChatBot and perform a single interaction with it. Conversion.java is a new class, so you'll need to make this one from scratch.

&nbsp;

For this project, you will update the code to accept a whole sentence from the user in your Main class. Once you read in the sentence from the user, your ChatBot will search the sentence for the following key words:

hello
name
favorite
quirk
height
weight
If you find the sentence has one of the key words, and only one, you'll have the chatbot reply with one appropriate response. If you find the sentence has two of the keywords, you'll make the chatbot respond to both keywords. If you find more than two keywords, it should only respond to two keywords. The order you pick the keywords doesn't matter. Which keywords the chatbot picks up on is up to you. So, in short:

Only 1 keyword = 1 response
Two keywords found = 2 responses.
More than 2 keywords = 2 responses
In example, if you say "Hello there chatbot!" ...when the chatbot looks through the sentence, it should see the word "hello" and respond to it. Specifically, it will respond with the replyHello() function.

If you instead say, "My name is Jared." then the ChatBot should respond with its own name. Specifically, it will respond with the replyName() function.

If you say two keywords in one sentence, for example: "My name is Tim. Do you have a favorite day of the week?" ...the chatbot should respond with both replyHello() and replyFavoriteDOW().

If the user says three keywords, in example: "Hello! Height wise, I'm tall. What about you? Do you have a quirk?" ...the chatbot should only respond to two of these keywords found (which are hello, height, quirk).

This checking of the users sentence will occur in the interact() function in ChatBot.java.

Your program should loop in main(), each time asking the user for a sentence. If the user types "exit" then the loop should end.

&nbsp;

You will make the following major changes to Main.java:

Keep the chatbot you created, but delete the call to your chatbot's interact() function.
In the main function, after the chatbot you originally created, Create a scanner for input.
Following that, add the following into the main function:
A loop that loops until the user enters the exact string "exit"
Add a call to your chatbot's interact function in the loop. Pass in the user's String sentence as a parameter.
You will make the following major changes to ChatBot.java:

In the ChatBot constructor, create an array. You will put five values for 'name' into it. Also create an array to hold 5 favorite hobbies for the Chatbot, an array to hold 5 values in it for possible favorite dotw, one with 5 quirks, one with 5 heights and an array with 5 weights. (Assume the doubles for heights you store are in feet.) Choose one value at random from each of these array to set each value in the ChatBot's memory. You can use a Random object (explained below) to choose a random number.
Modify interact(String userMessage) function to:
look through the user's message to the chatbot to find a keyword. You'll want to review our slides, lecture and code on Strings from Week 8 and Week 9 for how to do this.
Store the keywords you find in String variables. (If you find a need, you can use a String array to store what you find, or a String array.) From there you can use ifs or a switch block to check if the value of the string equals any of the keywords mentioned earlier. (If you think it would be easier to not store the variable, that's fine as well.) I
If a string you stored equals a keyword, print out that key word's reply function. Only reply to two keywords at max, as mentioned earlier.
If the string you stored does not contain a keyword, just have the ChatBot respond with the replyAskAboutUser() function.
You will modify replyHeight() as well. At the moment, you are only returning the height stored in your memory object. We will change this to make the height the Chatbot says a bit more random.
Create a Random object in replyHeight(). You will use the Random object to choose whether to have the Chatbot say it's height in feet (which should be the value you stored in memory) or in meters. Use the Conversion class's convertFeetToMeters() function to do so.
Once you have chosen to return either the height in feet or meters, have the Chatbot say it's height.

You will create a class called Conversion.java. This class will only contain a single static function called convertFeetToMeters(). Do not make an object of the Conversion class anywhere in your project. As it only contains a static function, you will call convertFeetToMeters from the class directly.

convertFeetToMeters() will accept a double as a parameter. Assume this double represents # feet tall someone is.
You will convert the number of feet passed in to meters.
Return a double representing the # meters tall the object is.
For reference on calling static functions, see: COP3503 - Random Class &amp; Static Functions.pptx

Actions

&nbsp;

Random Class - How Does it Work?

To use an instance of the Random class, you first must create an object of type Random.

Random rand = new Random();
Once you've created this object, you can choose a random number by calling the object's "nextInt()" function, and then store the result from that function in a variable.

If you do so, you'll notice the number it gives you is really large. This is because there are no limits on how high the value can go. Potentially, the random number can be as high as the biggest allowed integer in Java. To get around this, programmers will often manage the size of the result they get by modulating the result by the max number desired + 1.

i.e. if we want the function to return values from 0-X, we would use:

nextInt() % (X+1)
The number it returns may also be negative. If you want to make it so the value you get is always positive, consider using the Math.Abs() function.

(As a side note, unlike with C, the Random class seeds itself so there's no need to worry about that!)

For more info, see the following slides: COP3503 - Random Class &amp; Static Functions.pptxActions

&nbsp;

Goals

Get experience using and searching through Strings.
Get experience using arrays and the random class.
Get experience using static functions.
Get experience with loops.
Get experience with Modifying an existing custom class.

Sample Runs

Sample Program Run (user input is underlined)

Say something: What's your name?

My name is Tim!

&nbsp;

Say something: Do you have a favorite hobby?

I really like Reading and Mondays!

&nbsp;

Say something: Do you have a favorite hobby? What's your name?

I really like Reading and Mondays!

My name is Tim!

&nbsp;

Say something: Do you have a favorite hobby? What's your name? What's your height?

I really like Reading and Mondays!

My name is Tim!

&nbsp;

Say something: Do you work?

What about you? Care to tell me about yourself?

&nbsp;

Say something: ...

What about you? Care to tell me about yourself?

&nbsp;

Other Requirements

Commenting Standards:

Include javadoc comments for each function you make (including main()). Describe what each function is doing in their Javadoc comment.
Include a Javadoc comment for your class. Include your name, n-number, and project name and description of what the class/project does in this comment.
Include comments in your functions that explains complicated pieces of code. If the code seems easy to understand, then there's no need. But for hard to follow spots (i.e. multiple if's within if's), put in comments to explain what 's going on.
File Naming:

Please name your project "n#_Project3." Be sure to zip up your whole project and submit it here as "n#_Project3.zip!" (Also be sure to include your WHOLE Eclipse project in the zip! Not just the .java files!)
WHAT TO SUBMIT: When you submit your assignment, you should submit five files. First should be your .zip as usual. Your .zip file should contain all your code in their usual spots. Then, along with your .zip files, you will also need to submit all of your .java files as separate files.
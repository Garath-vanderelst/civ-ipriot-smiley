# Evidence and Knowledge

This document includes instructions and knowledge questions that must be completed to receive a *Competent* grade on this portfolio task.

## 1. Required evidence

### 1.1. Answer all questions in this document

- Each answer should be complete, well-articulated, and within the specified word count limits (if added) for each question.
- Please make sure **all** external sources are properly cited.
- You must **use your own words**. Please include your full chat transcripts if you use generative AI in any way.
- Generative AI hallucinates, is not an authoritative source

### 1.2. Make all the required modifications to the code

- Please follow the instructions in this document to make the changes needed to the code.

- When requested to upload evidence, upload all screenshots to `screenshots/` and embed them in this document. For example:

```markdown
![Example Running Code](screenshots/screenshot1.png)
```

![Sample](screenshots/sample.png)
> Note the `!`, and the use of a relative path.

- You must upload the code into your GitHub repository.
- While you can use a branch, your code should be in main when you submit.
- Upload a zip of this repository to Blackboard when you are ready to submit.
- You will be notified of your result via Blackboard
- However, if using GitHub classrooms, you may also receive additional feedback on GitHub directly

### 1.3. Optional: Use of Raspberry Pi and SenseHat

Raspberry Pi or SenseHat is **optional** for this activity. You can use the included `sense_hat.py` file to simulate the SenseHat on your computer.

If you use a Pi, please **delete** the `sense_hat.py` file.

### 1.4. Accessible version of the code

This project relies on visual patterns that appear on an LED matrix. If you have any accessibility requirements, you can use the `udl/accessible` branch to complete the project. This branch provides an accessible code version that uses text-based patterns instead of visual ones.

Please discuss this with your lecturer before using that branch.

## 2. Specific Tasks & Questions

Address the following tasks and questions based on the code provided in this repository.

### 2.1. Set up the project locally

1. Fork this repository (if not using GitHub Classrooms)
2. Clone your repository locally
3. Run the project locally by executing the `main.py` file
4. Evidence this by providing screenshots of the project directory structure and the output of the `main.py` file

![Local Execution (INSERT YOUR SCREENSHOT)](screenshots/running_main_q1.png)

If you are running on a Raspberry Pi, you can use the following command to run the project and then screenshot the result:

```bash
ls
python3 main.py
```

### 2.2. Fundamental code comprehension

 Answer each of the following questions **as they relate to that code** supplied by in this repository (ignore `sense_hat.py`):

1. Examine the code for the `smiley.py` file and provide  an example of a variable of each of the following types and their corresponding values (`_` should be replaced with the appropriate values):

   | Type                    | name           | value     |
   | ----------              |----------------|-----------|
   | built-in primitive type | dimmed         | True      |
   | built-in composite type | blank          | (0, 0, 0) |
   | user-defined type       | self.sense_hat | SenseHat  |

2. Fill in (`_`) the following table based on the code in `smiley.py`:

   | Object      | Type   |
   |-------------|--------|
   | self.pixels | list   |
   | Not Found   | str    |
   | self        | Smiley |

 
3. Examine the code for `smiley.py`, `sad.py`, and `happy.py`. Give an example of each of the following control structures using an example from **each** of these files. Include the first line and the line range:

   | Control Flow | File      | First line | Line range |
   | ------------ |-----------|------------|------------|
   |  sequence    | smiley.py | 15         | 12         |
   |  selection   | sad.py    | 26         | 4          |
   |  iteration   | happy.py  | 30         | 2          |

4. Though everything in Python is an object, it is sometimes said to have four "primitive" types. Examining the three files `smiley.py`, `sad.py`, and `happy.py`, identify which of the following types are used in any of these files, and give an example of each (use an example from the code, if applicable, otherwise provide an example of your own):

   | Type                    | Used? | Example                                    |
   | ----------------------- |-------|--------------------------------------------|
   | int                     | Yes   | all objects in the list mouth are integers |
   | float                   | Yes   | delay = 0.25                               |
   | str                     | No    | 'This is an example'                       |
   | bool                    | Yes   | dimmed = True                              |

5. Examining `smiley.py`, provide an example of a class variable and an instance variable (attribute). Explain **why** one is defined as a class variable and the other as an instance variable.



>  dim_display is an instance variable as it does not change across instances.
>  whereas self.pixels changes based on the Smiley being instantiated.
>

6. Examine `happy.py`, and identify the constructor (initializer) for the `Happy` class:
   1. What is the purpose of a constructor (in general) and this one (in particular)?

   > The initializer determines the fundamental attributes required to make an instance of that class.
   > This one in particular is a child of a Smiley and a Blinkable and as such requires the attributes and 
   > behaviours from them
   >

   2. What statement(s) does it execute (consider the `super` call), and what is the result?

   > By using the super call it ensures that the base requirements for Smiley and Blinkable are met
   > It also runs its own behaviours draw_eyes and draw_mouth
   >

### 2.3. Code style

1. What code style is used in the code? Is it likely to be the same as the code style used in the SenseHat? Give to reasons as to why/why not:

> The code style used here is PEP8, this is likely to be the same as used in sense_hat.py as they are both python files
> inside the same project. However if we are using a Raspberry Pi for this SenseHat would not be in PEP8 as it is 
> hardware.
>

2. List three aspects of this convention you see applied in the code.

> 1. snake_case for variable names
> 2. PascalCase for class names
> 3. 4 spaces are used for indenting
>

3. Give two examples of organizational documentation in the code.

> Line 12 of smiley.py is a comment on what the code is doing.
> Lines 29-32 of smiley.py is a docstring to describe the functions purpose and expected inputs.
>

### 2.4. Identifying and understanding classes

> Note: Ignore the `sense_hat.py` file when answering the questions below

1. List all the classes you identified in the project. Indicate which classes are base classes and which are subclasses. For subclasses, identify all direct base classes.
  
  Use the following table for your answers:

| Class Name | Super or Sub? | Direct parent(s)  |
|------------|---------------|-------------------|
| Smiley     | Super         |                   |
| Sad        | Sub           | Smiley            |
| Happy      | Sub           | Smiley, Blinkable |
| Blinkable  | Super         |                   |


2. Explain the concept of abstraction, giving an example from the project (note "implementing an ABC" is **not** in itself an example of abstraction). (Max 150 words)

> Abstraction is the idea that we only need to get the attributes and behaviours of an object that we will need.
> For example the Happy class defines the base characteristics of a happy face(eyes, mouth, the ability to blink).
> 
>

3. What is the name of the process of deriving from base classes? What is its purpose in this project? (Max 150 words)

> This is describing inheritance, It is used in this project to define parameters that a happy and a sad can have.
> This is useful because it saves re-writing the same code, which reduces the chance of errors and improves readability.
> In this code it means that the smiley and sad faces have the same colour scale and the same pixel map.

### 2.5. Compare and contrast classes

Compare and contrast the classes Happy and Sad.

1. What is the key difference between the two classes?
   > the Happy class has a second parent class in Blinkable that sad does not.
   >
2. What are the key similarities?
   > They both inherit from Smiley, they both have functions called draw_mouth and draw_eyes & they both 
   > call for the constructors of their parent(s).
   >
3. What difference stands out the most to you and why?
   > The secondary parent for Happy gives it additional funtionality. This functionality could in the future be used in
   > Sad, or any other new types of Smiley, however it is currently not.
   >
4. How does this difference affect the functionality of these classes
   > This ensures the Happy class has the blink function.
   >

### 2.6. Where is the Sense(Hat) in the code?

1. Which class(es) utilize the functionality of the SenseHat?
   > Smiley has the SenseHat functionality which means that Sad and Happy also have the ability to use it.
   > Smiley and Happy are the only two that use it.
   >
2. Which of these classes directly interact with the SenseHat functionalities?
   > Happy directly calls it on main.py lines 12 & 16
   >

3. Discuss the hiding of the SenseHAT in terms of encapsulation (100-200 Words)
   > Hiding and showing attributes from outside the class is basis of encapsulation. Hiding attributes is primarily done to avoid
   > relational classes from being able to edit the attributes. It is achieved in python by placing two underscores
   > before the attribute name. In this code sense_hat is not hidden and as such Happy.sense_hat will return data.
   > Whereas if it was hidden Happy.__sense_hat would not

### 2.7. Sad Smileys Can’t Blink (Or Can They?)

Unlike the `Happy` smiley, the current implementation of the `Sad` smiley does not possess the ability to blink. Let's first explore how blinking has been implemented in the Happy Smiley by examining the blink() method, which takes one argument that determines the duration of the blink.

**Understanding Blink Mechanism:**

1. Does the code's author believe that every `Smiley` should be able to blink? Explain.

> Not every Smiley should blink, and as such it is not built in to the Smiley class.
> We are able to create a blink function by adding it to any child class we create. 
> By using an abstract class to ensure the blinkable classes can blink as opposed to the other way around every Smiley
> has the ability to blink, even if not utilized.
>

2. For those smileys that blink, does the author expect them to blink in the same way? Explain.

> The blink speed is set in the instance of its call (delay). This tells me that the author wanted different Smileys to
> blink at different speeds. If they were all meant to blink at the same speed that would have been set in the Smiley
> class.
>

3. Referring to the implementation of blink in the Happy and Sad Smiley classes, give a brief explanation of what polymorphism is.

> Polymorphism is the ability to call a function on different classes. For the purpose of context based outcomes.
> 
> Blink is not an example of this as it is not a function of the Sad class. 
> 
>However, draw_mouth is. If you call draw_mouth on Happy, you will get a different outcome to if you called it on Sad.
> 
>

4. How is inheritance used in the blink method, and why is it important for polymorphism?

> 
> The blink method uses the show function of its parent. This gives us the ability to call the same function as defined
> in the parent class, the ability to call functions of the same name across different subclasses is polymorphism and
> by being defined in the parent this is ensured.
>
1. **Implement Blink in Sad Class:**

   - Create a new method called `blink` within the Sad class. Ensure you use the same method signature as in the Happy class:

   ```python
   def blink(self, delay=0.25):
       """
       Blinks the smiley's eyes once
        
        :param delay: Delay between blinks (in seconds)
        """
        self.draw_eyes(wide_open=False)
        self.show()
        time.sleep(delay)
        self.draw_eyes(wide_open=True)
        self.show()
   ```

2. **Code Implementation:** Implement the code that allows the Sad smiley to blink. Use the implementation from the Happy Smiley as a reference. Ensure your new method functions similarly by controlling the blink duration through the `delay` argument.

3. **Testing the Implementation:**

- Test the new blink functionality on your Raspberry Pi or within the Python classes provided. You might need to adjust the `main.py` script to incorporate Sad Smiley's new blinking capability.

Include a screenshot of the sad smiley or the modified `main.py`:

![Sad Smiley Blinking](screenshots/sad_blink.png)

- Observe and document the Sad smiley as it blinks its eyes. Describe any adjustments or issues encountered during implementation.

  > Initially after copying the code across, the blink function only closed the eyes of the sad face,
  > after importing 'time' the delay started working and it re-opened its eyes.

  ### 2.8. If It Walks Like a Duck…

  Previously, you implemented the blink functionality for the Sad smiley without utilizing the class `Blinkable`. Assuming you did not use `Blinkable` (even if you actually did), consider how the Sad smiley could blink similarly to the Happy smiley without this specific class.

  1. **Class Type Analysis:** What kind of class is `Blinkable`? Inspect its superclass for clues about its classification.

     > Blinkable is an abstract base class (ABC)

  2. **Class Implementation:** `Blinkable` is a class intended to be implemented by other classes. What generic term describes this kind of class, which is designed for implementation by others? **Clue**: Notice the lack of any concrete implementation and the naming convention.

     >This is commonly referred to as an abstract class. An abstract class cannot be created but ensures behaviours of its
     > child classes with the use of abstract methods

  3. **OO Principle Identification:** Regarding your answer to question (2), which Object-Oriented (OO) principle does this represent? Choose from the following and justify your answer in 1-2 sentences: Abstraction, Polymorphism, Inheritance, Encapsulation.

      > This is an example of Inheritance, as the child of this class assumes this attribute. 

  4. **Implementation Flexibility:** Explain why you could grant the Sad Smiley a blinking feature similar to the Happy Smiley's implementation, even without directly using `Blinkable`.

      > The Blinkable class is there to throw an error if the child class does not have the function blink.
      > this does not stop the Sad class from having that function. However, it ensures that classes that are meant to be
      >able to blink, are.

  5. **Concept and Language Specificity:** In relation to your response to question (4), what is this capability known as, and why is it feasible in Python and many other dynamically typed languages but not in most statically typed programming languages like C#? **Clue** This concept is hinted at in the title of this section.

  > This is known as ad-hoc polymorphism. It is feasible in dynamically typed languages because in those, data types are
  > not required to be explicitly stated, if an object has the required attributes then it will pass. If an object does 
  > not have the required attributes it will result in a runtime error.

  ***

  ## 3. Refactoring

  ### 3.1. Does a Smiley Have to Be Yellow?

  While our current implementation predominantly features yellow smileys, emotional expressions like sickness or anger typically utilize colors like green, red, or orange. We'll explore the feasibility of integrating these colors into our smileys.

  1. **Defined Colors and Their Location:**

     1. Which colors are defined and in which class(s)?
        > White, Green, Red, Yellow are all defined in the Smiley class
     2. What type of variables hold these colors? Are the values expected to change during the program's execution? Explain your answer.
                
        > These are class variables, they are constant and as such we do not expect them to change
        > 
     3. Add the color blue to the appropriate class using the appropriate format and values.

  2. **Usage of Color Variables:**

     1. In which classes are the color variables used?
        > Smiley, Happy and Sad

  3. **Simple Method to Change Colors:**
     1. What is the easiest way you can think to change the smileys to green? Easiest, not necessarily the best!
     > Easiest would be to set YELLOW to (0, 255, 0)



  ### 3.2. Flexible Colors – Step 1

  Changing the color of the smileys once is straightforward, but it isn't very flexible. To facilitate various colors for smileys, it is advisable not to hardcode values in any class. This approach was identified earlier as a necessary change. Let's start by removing the built-in assumptions about color in our classes.

  1. **Add a method called `complexion` to the `Smiley` class:** Implement this instance method to return `self.YELLOW`. Using the term "complexion" instead of "color" provides a more abstract terminology that focuses on the meaning rather than implementation.

  2. **Refactor subclasses to use the `complexion` method:** Modify any subclass that directly accesses the color variable to instead utilize the new `complexion` method. This ensures that color handling is centralized and can be easily modified in the future.

  3. **Determine the applicable Object-Oriented principle:** Consider whether Abstraction, Polymorphism, Inheritance, or Encapsulation best applies to the modifications made in this step.

  4. **Verify the implementation:** Ensure that the modifications function as expected. The smileys should still display in yellow, confirming that the new method correctly replaces the direct color references.

  This step is crucial for setting up a more flexible system for color management in the smiley display logic, allowing for easy adjustments and extensions in the future.

  ### 3.3. Flexible Colors – Step 2

  Having removed the hardcoded color values, we now enhance the base class to support dynamic color assignments more effectively.

  1. **Modify the `__init__()` method in the `Smiley` class:** Introduce a default argument named `complexion` and assign `YELLOW` as its default value. This allows the instantiation of smileys with customizable colors.

  2. **Introduce a new instance variable:** Create a variable called `my_complexion` and assign the `complexion` parameter to it. This step ensures that each smiley instance can maintain its own color state.

  3. **Rationale for `my_complexion`:** Using a distinct instance variable like `my_complexion` avoids potential conflicts with the method parameter names and clarifies that it is an attribute specific to the object.

  4. **Bulk rename:** We want to update our grid to use the value of complexion, but we have so many `Y`'s in the grid. Use your IDE's refactoring tool to rename all instances of the **symbol** `Y` to `X`. Where `X` is the value of the `complexion` variable. Include a screenshot evidencing you have found the correct refactor tool and the changes made.

  ![Bulk Rename](screenshots/X_Factor.png)

  5. **Update the `complexion` method:** Adjust this method to return `self.my_complexion`, ensuring that whatever color is assigned during instantiation is what the smiley displays.

  6. **Verification:** Run the updated code to confirm that Smileys still defaults to yellow unless specified otherwise.

  ### 3.4. Flexible Colors – Step 3

  With the foundational changes in place, it's now possible to implement varied smiley colors for different emotional expressions.

  1. **Adjust the `Sad` class initialization:** In the `Sad` class's initializer method, change the superclass call to include the `complexion` argument with the value `self.BLUE`, as shown:

     ```python
     super().__init__(complexion=self.BLUE)
     ```

  2. **Test color functionality for the Sad smiley:** Execute the program to verify that the Sad smiley now appears blue.

  3. **Ensure the Happy smiley remains yellow:** Confirm that changes to the Sad smiley do not affect the default color of the Happy smiley, which should still display in yellow.

  4. **Design and Implement An Angry Smiley:** Create an Angry smiley class that inherits from the `Smiley` class. Set the color of the Angry smiley to red by passing `self.RED` as the `complexion` argument in the superclass call.

  ***

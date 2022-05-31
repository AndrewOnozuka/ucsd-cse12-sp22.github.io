---
layout: with-sidebar
index: 11
name: Exam 3
released-on: "2022-05-27"
---
# Exam 3

### Release: 8am Friday May 27, 2022
### Due: 8am Sunday May 29, 2022

**We will not accept late submissions. There will be no exceptions.**

This page details a take-home exam that you will complete over the next few
days. You can’t communicate with anyone about the content of the assignment
until the exam has concluded. **DO NOT** post clarification or other similar questions as staff will not be answering these types of questions during this time period. If there are broken links or otherwise strange parts of the writeup, you may post these concerns on piazza. If you have technical trouble creating a screencast (detailed below) feel free to reach out for assistance.

Do not use any online service other than Piazza to ask questions about the
assignment. Do not search for, solicit, or use solutions to the problems that
you find elsewhere for the exam. These are all violations of academic integrity
that students have committed on exams like this in the past.

You can make use of any course notes, online resources about Java and its
libraries, Java tools, and so on to complete the exam, including re-using code
from class notes or PAs.

You can review the grading policy for exams in the [syllabus](https://ucsd-cse12-sp22.github.io/syllabus.html).
You will complete the programming task below and submit your work to the `Exam1` Gradescope assignment.

Starter code is available here:

[https://github.com/ucsd-cse12-sp22/Exam3-starter](https://github.com/ucsd-cse12-sp22/Exam3-starter)

Submission checklist (see long descriptions below for full details):

- [ ] `CircularArrayList.java`
- [ ] `CircularArrayListTest.java`
- [ ] `MaxHeap.java`
- [ ] `MyHashMap.java`
- [ ] `MyHashMapTest.java`
- [ ] `FileReader.java`
- [ ] `video.*` (`*` means whatever extension you have; we *really* prefer `mp4`, which is what Zoom produces. If you use an extension other than mp4, check that it plays in Gradescope!)

Make sure to look at your Gradescope submission after submitting to see if all the required files are there.


### **Task 1 and 2 will be autograded(except testcases). Task 3 will be manually graded** 

Make sure that your submission passes autograder for your code to be properly graded. 

If you are having issues with getting the autograder to run successfully, you may find it helpful to consult the [Developing with the Gradescope Autograder in Mind](https://docs.google.com/document/d/1IKSDkG4kHC0gb2FyqdeOWJOAbQr6UCvYZSToIBopfVs/edit?usp=sharing) guide.

If your submission passes the autograder, then you should see output similar to:

<img src="autograder_success.png">{:width="100%"}

Be aware that the Compile check does not check for code correctness, but rather that your code compiles. Additionally, if your code errors or throws exceptions unexpectedly, the autograder will not grade your submission. This will result in 0 points being given for that particular task.

Your submission will be graded **after** the deadline. You should test thoroughly yourself to make sure your program works as expected.

## Clarifications

**Can I use a Java feature/library/method that we haven't covered in class?**

Yes (unless otherwise specified), just make sure it doesn't break the autograder. The course staff is not responsible for fixing any submissions that fail the autograder during or after the exam. 

**Can we write more methods than specified?**

Yes, you can write additional helper methods.

**Can I use previous code that I wrote for a PA in my exam?**

Yes.


## Task 1 – MaxHeap and HashMap

You will be given set of student details. (Sample in `input.txt`). The student class is given for you. Each student has a name, section and marks details.
We want to store the student details in a HashMap, such that all students in the same section fall in the same bucket. Further, we want to find out the maximum marks obtained in each section. It is an interesting idea to use MaxHeap for each bucket(section), so that you can easily retrieve the maximum. You will be implementing this functionality in this task.

You will be writing your code in `MaxHeap.java`, `MyHashMap.java` and `FileReader.java `. The `MyHashMap.java` will be implementation of your hashMap that implements the given `DefaultMap` interface given. 

You have used ArrayList earlier for the buckets in HashMap. Now you will be creating every bucket using the MaxHeap datatstructure. For this you are first required to complete the methods in the `MaxHeap.java`. These methods can be used in coding yourHashMap buckets.

### Task 1.1 MaxHeap add, peek, remove
You will implement 3 methods in `MaxHeap.java`, these can further use other helper methods like BubbleUp, BubbleDown, etc as taught in the lecture.
The `add` method will take in the key and value values and add in the MaxHeap. Make sure the MaxHeap property is satisfied after adding each element, to know you are procedding correctly.
The `peek` method will return the top(maximum) element of your MaxHeap, this does not remove the element.
The `remove` method will remove and return the top(maximum) element of your MaxHeap. Make sure the MaxHeap property is satisfied after removing each element.
The hashMap constructor also takes a comparator, which can be used to compare the elements. Further details can be infered from the starter code.

### Task 1.2 FileInputStream
The `FileReader.java` class is used to read the student details.
You will implement 2 methods in `FileReader.java`, these can further use other helper methods.
The `createHeap` method will read in the student details from the `input.txt` file and store the student entries in the HashMap. Use java FileInputStream to read the file.
The `getMaxOfSection` method will return a student who scored maximum score in a given section. In case the section is not present, it must return null.
Make sure to define a Student comparator and HashMap object in your FileReader constructor.

### Task 1.3 HashMap
You are required the implement the DefaultMap interface methods in the `MyHashMap.java`. It is similar to PA6, but you are required to use a MaxHeap  instead of ArrayList for the buckets. The get() method should return the peek() value of the bucket.
Make sure to write proper hashFunction to map the Student to the bucket (section of the student). 
You are not required to implement reshash functionality for this Exam. You can consider a fixed size HaspMap of around 10 buckets, as the number of sections is limited. So loadfactor is not needed for the exam.

You further have a `HashMapTest` file that can be used to test your code locally.

### Task 1.4 TestCase
**Do not add any other junit import statements in the test file**
Write testcases to check max score of atleast 2 sections as per the input.txt  in `HashMapTest` file.

## Task 2 – CircularArrayList
**You may not import Java's builtin ArrayList or LinkedList to complete this task**

You will be writing your code in a file called `CircularArrayList.java`. You will implement all the methods from `ArrayListADT` interface. 
The `addRear` method will add elements towards the rear of the array.
The `addFront` method will add elements towards the front of the array. This is similar to the `start` mentioned in the lecture.
The `remove` method will always remove the first element (start index).
The `get` method will return the element at a given index, remember that the start index will have the 0th index element. Throw an exception stating "Element doesn't exist", in case the element is not present.
You are also required to implement the `extendCapacity` method for the circularArrayList. Start with initalCapacity of 100, and double everytime expandCapacity.

You further have a `CircularArrayListTest` file that can be used to test your code locally.
**Do not add any other junit import statements in the test file**
Write testcases to check elements present at few positions (atleast2) in `CircularArrayListTest` file.

## Task 3 - Video

You will record a short video of no more than 10 minutes. You are not expected to use the entirety of the allotted time, but it is given to provide enough buffer for you to complete the video task.

Tip: If you find yourself running out of time, you might be explaining your code too much. If the task does not ask you to directly explain your code, you don't need to explain it. 

Include:

- Show only your face and a picture ID (your student ID is preferred but any
picture ID with your name on it will work) for a few seconds at the beginning.
You don’t have to be on camera the whole time, though it’s fine if you are. Just
a brief confirmation that it’s you creating the video/doing the work attached to
the work itself is what we want. If you do not have a webcam, take a picture of
yourself (and your picture ID) with your phone and display that picture at the
start of your screen share.
- You must also verbally explain your thought process as you complete the following tasks.
- You may use any technology to create the memory diagrams.

**Note**: Gradescope has a max file size of 100MB. Any files larger than this will be rejected. We will **NOT** accept any files (code, videos, etc.) outside of the gradescope submission. Additionally make sure that you are able to play your video on gradescope. If your video is not playable on gradescope by staff, then it will not be graded and given a score of 0.

To reduce video file sizes:
- Use zoom
    - A 100MB video is about a 20 minute video on Zoom (1620x1080 video resolution).
    - If you are not using Zoom, convert your file to an MP4 (there are web tools that can do this). MP4 videos have smaller video sizes than other video formats.
- Use a smaller screen size for your computer, or only record a smaller portion of the screen.
- Reduce background clutter (i.e. desktop icons). Background clutter reduces compression, making larger file sizes. You can hide the background by maximizing your code editor window.
- Keep your video short. 
    - 10 minutes is the max, it’s possible to cover everything in less time
    - Create a script of what you are going to say.
    - Pause the video as you switch to the code for the next question (make sure to tell us which question you are showing the code for when you switch).
- Use a 3rd party video editor to reduce the width/height of the video, but make sure your code isn't blurry when you play it on Gradescope as we cannot grade blurry videos.


### Task 3.1 MaxHeap and HashMap
- You are required to calculate the runtime equation and runtime complexity for the get and put methods of your implementations. 
- Compare the runtime for the MaxHeap case vs case where the bucket is arraylist. (no need to code this)
- Also consider a situation, where you are supposed to also search for a students record in a bucket in logn complexity. What datastructure will be most apt to represent the bucket? Reason in your video.

### Task 3.2 CircularArrayList
- You must mention how this implementation of ArrayList improves your list performance.
- Also compare the runtime complexity for circularArrayList vs ArrayList implementation for the add and remove methods. What do you observe?

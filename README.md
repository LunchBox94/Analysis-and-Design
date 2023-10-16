# Analysis-and-Design
Project One / Project Two

Brennan Haggett
10/02/2023


1.	open a file

2.	read the data from a file


3.	parse each line, and check for file format errors

4.	define an object to hold data from an input file in the appropriate data structure


5.	print out information from a data structure that meets requirements



#1  Vector Data Structure

File Input


Function OpenCourseFile (filename: String) 
Try
	Open 'filename' for reading as 'file'     / / Read the file
	If “file” cannot be opened
	Print “Error cannot open file”
	Exit Function
End Try

Course Object Pseudocode

// Defining the course objects that will be holding the course data

Class Course
	String courseNumber
	String courseTtile
	Vector <String> prerequisites   // This will vector will be used to store the prerequisites

// Using a Constructor to load course data

Constructor Course(courseNumber: String, courseTitle: String)
	obj.courseNumber = courseNumber
	obj.courseTitle = courseTitle
	obj.prerequisites = Vector<String>()
End Constructor
End Class

// Creating an empty vector which is for Course objects

Vector <Course> courses

// Read all the lines and process each line from the input file

While the is not done being read
	Read next line from the “file”

// Separate the “lines” into courseNumber, courseTitle, and prerequisites 

courseData = spliteLineWith Commma(line)
// Course data will need two elements within it

If elements of the courseData >= 2
	course = New Course(courseData[0], courseData[1])
	For i from 2 to elemnts of courseData – 1
		course.prerequisites.Add(courseData[i])
	End 
		courses.Add(course)
	End If
	End While




Print Course Information Pseudocode

// Define a function that will print the course information as the requirements demand

Function printCourseInformationByRequirements(requirements) {
	For Each course within courses
	If course.meetsRequirements(requirements)
		Print "Course Number: " + course.courseNumber
		Print "Course Title: " + course.courseTitle
		If course.prerequisites.Length > 0
			Print "Prerequisites:"
			For Each prerequisite In course.prerequisites
				Print " " + prerequisite
End This
Else
	Print "No prerequisites."
End 
}



#2 Hash table data structure




File Input


// Open and read file

Function Readfile {
	OPEN file with the (filename)
	IF the file has been OPEN 
		READ file
		RETURN file handle
Else:
OUTPUT “ERROR: Was not able to open file”
RETURN
END


Course Object Pseudocode

// Define course object structure
Object Course {
STRING courseNumber
STRING courseTitle
LIST prerequisites

// Create course as a hast table

Function CreateHashTable(size) {
	CREATE empty hashTable of size ‘size’
}

// Add courses to Hash Table

Function addToHashTable (hastTable, course) {
	INDEX = HASH(course.courseNumber) (hasttable.size)
	Append course TO hashTable.bucket [INDEX]
}

// Retrieve Course from the created Hash Table
Function getFromHashTable (hashTable, courseNumber) {
	INDEX = Hash (CourseNumber) “hashTable.size”
	FOR each course IN the table.bucket [INDEX]
		IF the course.courseNumber is the same courseNumber THEN 
	RETURN course 
}
RETURN NULL

}
	

Print Course Information Pseudocode

// Print Course Information and prerequisites

Function printCourseInfor(Course) {
Print “Course Number”
Print “Title”
Print “prerequisites”
FOR EACH prerequisites IN the course {
	Print prerequisites.courseNumber + prerequisite.title
	}
}
END



#3  Tree data structure pseudocode
File Input


// Open and read file
Open and read file “course information file” 
If file is not opening
	Display ERROR message and exit
ELSE
	Create empty tree data structure “CourseTree”
WHILE there is a line in the file read each line
ELSE end

IF the number of tokens less than 2
Display error message and continue.
 END IF
IF the first token is not a number
  Display error message and continue.
END IF

IF third token exists
IF the third token is not a number
 Display error message and continue.
 ELSE IF the third token is not found in "courseTree"
 Display error message and continue.
END

Course Object Pseudocode

// Define course object structure
CREATE Course { 
string courseNumber
 string courseTitle 
string prerequisite 
}
// Initialize an empty binary tree
Course courseTreeRoot = null

// Function to read and insert data from the input file for binary tree
function read and insert course(fileName) {
OPEN fileName for reading
IF file does not exist THEN
 Display error message and exit the program
END IF

WHILE a line exists in file DO
Read line from file 
Split the line into courseNumber, courseTitle, and prerequisite

// Set prerequisite to "None" if it's empty 
IF prerequisite is empty THEN 
prerequisite = "None" 
END IF

Print Course Information Pseudocode

// Function for printing course information
function print_course_information(course) { 
IF course is not null THEN 
// Display the course number, title, and prerequisite 
Display "Course Number:", course.courseNumber 
Display "Course Title:", course.courseTitle 
Display "Prerequisite:", course.prerequisite 
END


Pseudocode for Menu

Menu that will be displayed for users-
1.	Load Data Structure
2.	Print Course List
3.	Print Course
4.	Exit

Repeat the actions until the user chooses to exit the program: 
The user has an option to choose from choose (1 – 4).

If the user chooses option 1:
	Give the user a path to data files.
	Load all course data from the file into the list.
	Display a message of success.
If the user chooses option 2:
	If the list is empty, THEN present an error message to the user
	ElSE
 		Sort the list alphabetically by the course title.
		Display all sorted list of the Computer Science courses.
If the user chooses option 3:
	If the list is shown to be empty, THEN show an error message to the user.
	Search the show list for the course with the correct code.
	IF found THEN display the course title and the course prerequisites.
	IF the course title and the prerequisites are not found THEN show “course is not found” message to the user.		
	
If the user chooses option 4:
Exit the program.


Alphanumeric order

PrintSortedCourses(dataStrucutre);
Sort(CourseList) = dataStructure.getCourses()
Sort(courseList) // Sort the courses by alphanumerical order

For every course in the courseList:
	Print(course.title)
	Print("Prerequisites: " + course.prerequisites)
End for
End Function

Function Sort(courseList):
	// Sort the courses by alphanumerical order
   	 Sort(courseList)  // Implement sorting algorithm here
End Function


Run-Time Evaluation

Vector	  Line Cost	Time Executed	Total Cost
Opening files and reading them	1	1	1
Check the course number 	1	1	1
Check the course title	1	n	n
Create course objects	1	n	n
Searching courses	1	1	1
Parsing each line	1	n	n
Print course information	1	n	n
Store data	1	1	1
			


Hash Table	Line Cost	Time Executed	Total Cost
Opening files and reading them	1	1	1
Check the course number	1	1	1
Check the course title	1	n	n
Create course objects	1	n	n
Searching courses	1	n	n
Parsing each line	1	n	n
Print course information	1	n	n
Store data	1	1	1
			



Binary Search Tree	Line Cost	Time Executed	Total Cost
Variables: left and right	1	1	1
Root = null	1	1	1
Creating course variables	1	1	1
Check course number	1	n	n
Check course title	1	n	n
Opening and reading file	1	n	n
Parsing each line	n	n	n
Print results	1	1	1


			Advantages and Disadvantages


Vectors, also known as dynamic arrays, offer advantages such as fast and direct element access, sequential memory storage for efficient iteration, and dynamic resizing capabilities. However, they have downsides, including potential overhead during resizing and inefficiency in inserting or deleting elements within the array, particularly in the middle. Additionally, vectors come with a fixed capacity that may not suit scenarios demanding dynamic memory allocation.
Hash tables excel in providing rapid key-based data retrieval with an average-case O (1) lookup time. They support diverse key types, adapt to dynamic data sizes, and handle insertions and deletions efficiently. Nonetheless, they don't maintain any specific order of data, making them unsuitable for ordered data scenarios. Handling collisions, when multiple keys hash to the same location, is also a consideration, and designing effective hash functions can be complex.
Binary search trees maintain data in sorted order, making them ideal for ordered data requirements. They enable efficient searches with an average-case O (log n) complexity, and well-balanced trees offer consistent performance. However, managing balancing in BSTs can be challenging, leading to poor performance if not maintained properly. Unlike vectors, BSTs don't support direct element access by index, and resizing requires manual intervention. In worst-case scenarios, when the tree is unbalanced, search operations can degrade to O(n) complexity.
Binary Trees vs. Linked Lists vs. Hash Tables
https://www.baeldung.com/cs/binary-trees-vs-linked-lists-vs-hash-tables


Recommendation

My recommendation will be a vector.  I recommend this data structure for the Computer Science advising program due to its simplicity, efficiency, and straightforward implementation. Vectors have an uncomplicated design that is very easy to work with and design. This creates an easy-to-point data structure that can be used for a wide number of people and applications. Where the number of courses is expected to be manageable, simplicity is a valuable feature. Vectors are intuitive to use, which will minimize the likelihood of errors and reduce the complexity of the code, making the experience better for the user. This feature will provide a maintainable program and code in the long term, making it more accessible for future updates. Vectors are memory-efficient, requiring less overhead compared to hash tables and binary search trees. 



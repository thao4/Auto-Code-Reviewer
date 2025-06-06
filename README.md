﻿# Auto-Code-Reviewer

This Java project automates the grading process for student submissions by running unit tests dynamically. It uses the JUnit 5 testing framework to evaluate Java assignments and display detailed test results for each submission.

Features
Dynamically tests student submissions for specific test cases.
Organized submission structure for efficient grading.
Real-time test feedback using JUnit's DynamicTest and DynamicContainer.
Handles errors caused by misconfigured directories or missing files.
Streamlined debugging process with clear error messages.
Setup Instructions
Prerequisites
Install the Extension Pack for Java in Visual Studio Code.
Ensure Java and Maven are installed and configured properly on your system.
Folder Structure
Organize your project directory as follows:

AssignmentName/  
│  
├── Submissions/  
│   ├── Group1/  
│   │   └── Assignment1.java  
│   └── Group2/  
│       └── Assignment2.java  
│  
├── src/  
│   └── test/  
│       └── java/  
│           └── com/  
│               └── reviewer/  
│                   ├── GraderTest.java  
│                   └── SetupTest.java  
│  
└── pom.xml  
Placing Submissions
Navigate to the Submissions folder.
Create a subfolder for each group (e.g., Group1, Group2, etc.).
Place the .java files inside the respective group folders.
Example:

Submissions/  
├── Group1/  
│   └── Assignment1.java  
└── Group2/  
    └── Assignment2.java  
Important: The directory structure must follow this format. Otherwise, the code will fail to locate the submissions.

Running the Tests
Step 1: Open the Project
Open Visual Studio Code.
Select File > Open Folder.
Navigate to the folder containing the assignment and open it.
Step 2: Locate the GraderTest.java File
Navigate to:
src/test/java/com/reviewer/GraderTest.java.
Open the file in VS Code.
Step 3: Compile the Tests
Open the command palette (Ctrl+Shift+P or Cmd+Shift+P).
Select Clean Java Language Server Workspace.
Recompile the project twice to ensure all files are detected.
Step 4: Run the Tests
Locate the Testing tab on the VS Code sidebar.
Expand the Java Test dropdown.
Select the desired test group and expand it to see individual submissions.
Expand the submissions to view their test case results.
Debugging Common Issues
1. Tests Folder Contains Non-Java Files
Ensure the Tests directory (if present) only contains .java files.

2. Directory Mismatch
Verify that the directory paths inside GraderTest.java align with your folder structure for submissions and test files.

3. pom.xml Issues
If errors persist, your pom.xml file may require updates. Copy the file and consult ChatGPT or any AI coding tool for troubleshooting Maven dependencies.

Code Structure
GraderTest
The primary test file dynamically generates tests for each submission.

Key Methods:
graderTest()

Organizes test cases for each group and creates dynamic containers for grading.
fizzTest(String groupNameFilter, String fileName)

Generates specific test cases for the FizzBuzz problem.
Test Flow:
Test groups are filtered by name.
Test cases are generated dynamically using DynamicContainer and DynamicTest.
Results are displayed in the Testing tab.

Example Test Cases
The fizzTest() method checks the output of the convert() method against these inputs and expected results:

Input	Expected Output
-1	N/A
2	2
3	Fizz
5	Buzz
6	Fizz
9	Fizz
15	FizzBuzz

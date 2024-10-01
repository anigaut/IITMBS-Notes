---
title: Software Testing Terminology
---
The Wikipedia definition of Software Testing is:
>Software testing is the act of checking whether software satisfies expectations. Software testing can also provide an objective, independent view of the software to allow the business to appreciate and understand the risks of software implementation.
# Common Terms
Here are some other commonly used terms in the testing domain:
	- **Validation**: The process of evaluating software at the end of software development to ensure compliance with intended usage. i.e., checking of the software meets its requirements.
	- **Verification**: The process of determining whether the products of a given phase of the software development process fulfil the requirements established at the start of that phase.
	- **Fault**: A static defect in the software. It could be a missing function or a wrong function in code.
	- **Failure**: An external, incorrect behavior with respect to the requirements or other description of the expected behavior. A failure is a manifestation of fault when software is executed.
	- **Error**: An incorrect internal state that is the manifestation of some fault.

A test case is an input given to a testing module that verifies whether the software being tested produces the expected output. If the actual output matches the expected output, the test case is said to have passed. Otherwise, it will be failure.
# Types of Testing
There are many different types of testing, depending the stage of the SLDC:
	- **Unit Testing**: Testing individual methods or components, usually done by the developer while coding it up.
	- **Integration Testing**: Testing of various components and modules combined.
	- **System Testing**: A test of how all the various components and parts of a codebase interact together in the system as a whole.
	- **Acceptance Testing**: Done by end-users to ensure that the final product meets requirements and expectations.
	- **Beta Testing**: Testing done by a select group of potential users to uncover bugs and other issues before release to a general audience.

The following diagram demonstrates how these types are related:
![[testing_types.png]]
- If `class A` and `class B` are developed by different developers, unit testing would be the testing of the individual methods on their own, which is done as when the methods are written.
- The lines that connect the methods represent the interface that connect the methods and allow them to work together. Integration testing is when these methods are combined using the interfaces and tested together.
- System testing would put all these methods together and test `main class P` which is the parent class.
- Some other types of testing are:
	- **Functional Testing**: Ensures that the code meets its expected functionality.
	- **Stress Testing**: Evaluates how the system performs under unfavourable and hostile conditions (extremely high traffic or old hardware, for example).
	- **Performance Testing**: Evaluates whether the speed and response timing meet expectations.
	- **Usability Testing**: Checks the UI, accessibility and so on.
	- **Regression Testing**: Done after modifying/upgrading a component, to ensure that the modification is working correctly and other components are not damaged by the modification.
# Testing Methods
- **Black-Box Testing**: Examination of the working and usability of the software without looking into the code.
- **White-Box Testing**: Testing the software by looking into internal structure, design and code.
# Types of Test Activities
- **Test Design**: This involves creating and formulating the test cases and testing process from beginning to end. Beyond specifying the inputs, the expected outputs need to be made clear too. This cannot be automated and requires significant domain knowledge in the field being operated in, like Banking, Social Media and so on.
- **Test Automation**: Involves converting the test cases into executable scripts. There are several FOSS and proprietary tools for this.
- **Test Automation**: Running the tests on some tool and recording the results.
- **Test Evaluation**: Evaluating the results of testing and identifying the errors in the code. Isolating errors is a hard task, especially in large codebases.
# Levels of Testing
- There are four levels of testing that organizations typically operate in:
- **Level 0**: Firms operating in this stage treat testing the same as debugging the strive merely to deliver code that syntactically correct without worrying about inherent issues in the code even thought it may contain inherent issues.
- **Level 1**: The objective of those at this level is to merely prove that the code is correct, without paying attention to the quality of tests and having a proper framework for testing. For example, if testing shows that the code is good, how do we know whether this is because the code is genuinely good or because the tests were designed poorly?
- **Level 2**: At this level, the purpose is to highlight failures and hunt for mistakes. This is a fundamentally negative perspective and puts testers and developers at odds with each other. 
- **Level 3**: A more refined version of the previous level, where firms adopt a more holistic perspective such that developers and testers cooperate to reduce errors and risk.
- **Level 4**: Testing is treated as a separate discipline and an integral part of the development process and is included in every step of the way. The primary responsibility of testing is to measure and improve the quality of software.

- Two important parts of testing are Controllability and Observability. The former refers to how inputs can be provided to the module being tested and the tests can be run using those inputs. The latter, on the other hand, refers to how the module being tested can be observed and to check if the module behaves as expected. 
- Let's say we have a somewhat complex code block like the following:

```
someMethod(){
	// line 1
	// line 2
	if { ...
	} else {
		while {...}
	}
}
```

- Suppose we'd like to test the `while` loop inside the `else` block, controllability means how we can reach the while loop and set up the variables needed to get there while observability refers to how we can record the results of the tests conducted on the loop and verify its performance.
> **SENG 637 - Dependability and Reliability of Software Systems**

**Lab. Report \#1 – Introduction to Testing and Defect Tracking**

| Group: 17            |
| -------------------- |
| Student 1 Brandon    |
| Student 2 Mustayeen  |
| Student 3 Mevin      |
| Student 4 Kate       |
| Student 5 Nur-Alhuda |

**Table of Contents**

(When you finish writing, update the following list using right click, then
“Update Field”)

[1 Introduction 1](#_Toc439194677)

[2 High-level description of the exploratory testing plan 1](#_Toc439194678)

[3 Comparison of exploratory and manual functional testing 1](#_Toc439194679)

[4 Notes and discussion of the peer reviews of defect reports 1](#_Toc439194680)

[5 How the pair testing was managed and team work/effort was
divided 1](#_Toc439194681)

[6 Difficulties encountered, challenges overcome, and lessons
learned 1](#_Toc439194682)

# Introduction

In this report, we will be testing two versions (1.0 and 1.1) of an ATM System. Our testing methodology include using exploratory, scripted, and regression testing techniques. Throughout this process, we document any identified bugs using Azure.

In the exploratory testing, we will uncover hidden defects and issues that formal test cases may overlook, effectively simulating real-world user behavior and adapting readily to evolving requirements. In contrast, the manual functional testing adheres to a scripted format that employs the predetermined test cases to ensure the software functions as intended. By integrating these testing methodologies, we aim to achieve a thorough and effective coverage, addressing various aspects of software quality in the development of the ATM System.

# High-level description of the exploratory testing plan

This Test Plan has been established to highlight the scope, methodology, for all testing work undertaken for the ATM simulation system. It delineates the items and features slated for testing such as types, strategy and scope for testing, logistics, comparison between exploratory & manual testing, and notes during peer reviews.

## 1.1 Types of Testing:

For each of the key operations, functions and areas for SUT defined above, the following strategy is defined for the Manual Non Scripted testing. Common paths and exceptional paths are defined within the cases.

### 1.1.1 Exploratory (Manual Non-scripted) Testing:

Objective: This testing type involves a spontaneous, investigative approach where testers explore the system without pre-defined scripts or test cases.

Approach: Testers familiarize themselves with the requirements and create a high-level test plan. This plan will outline the functions to target, the testing approach (e.g., breadth-first or depth-first), and strategies for generating test cases (focusing on common or exceptional paths).

Defect Reporting: Testers will record and report defects as they are discovered during the testing process. This phase emphasizes immediate documentation of defects to ensure no details are lost.

### 1.1.2 Manual Scripted Testing

Objective: This testing involves executing pre-defined test cases that are listed in a test suite. It aims to verify that the system behaves as expected according to the specified requirements.

Approach: A structured approach where the work in done in pairs; a team member operates the system under test while the other member tracks the test execution, reports defects, and decides the order of test execution. Test cases from the provided test suite are executed systematically.

Defect Reporting: Defects discovered during this phase are reported with a specific identifier (e.g., “MFT:” prefix). This helps differentiate them from defects found during exploratory testing.

### 1.1.3 Regression Testing (Verification of Defect Fixes)

Objective: This testing type focuses on retesting the system after defects have been fixed to ensure that the fixes are successful and that no new issues have been introduced.

Approach: The previously reported defects are divided among team members for individual retesting. This phase ensures that the changes made to the system have not adversely affected existing functionalities.

Defect Verification: Each team member is responsible for verifying the resolution of assigned defects and ensuring that the system still meets its requirements post-fixes.

## 1.2 Scope of Testing

The chosen exploratory testing plan for the ATM System Under Test (SUT) Version 1.0 is designed to evaluate the system's key functionalities, which are essential for both end-users and operators.

### 1.2.1 Feature to be tested

The following features of the ATM SUT V1.0 defined in software requirement specifications are to be tested, not necessarily in the order provided:

1. Card and PIN Validation: Verify the system's response to correct and incorrect Card and PIN entries. For PIN, test the behavior after three consecutive incorrect PIN attempts (card retention).
2. Cash Withdrawal: Validate multiple withdrawal transactions in multiples of $20 and check for approval.
3. Deposits: Test the acceptance of envelope deposits and the accuracy of entered deposit amounts.
4. Money Transfers: Verify money transfers between different linked accounts.
5. Balance Check: Verify that accurate balance information is provided for various accounts.
6. Transaction Abortion: Test the functionality of the 'Cancel' key during different stages of transactions.
7. Receipt Generation: Verify that the receipt contains correct details (date, time, location, transaction type, accounts, amounts, balances). Test for different transactions and ensure the printer's functionality.
8. Operator Controls:Test the key-operated switch for starting and stopping the machine. Verify the functionality when switching the machine to the "off" position (shutdown process).
9. Internal Transaction Log: Ensure all necessary transactions are logged appropriately.
10. Bank Communication: Validate communication protocols for each transaction type, including success and failure scenarios.
11. Software Failure Handling: Test the system's response to software failures during transactions.

### 1.2.2 Features That Might Not Require Immediate Testing

1. Physical Components: Check the deposit envelope slot functionality as this would be a physical component in reality.
2. Security Testing: Security and penetration testing is outside the scope of initial exploratory testing.
3. User Interface Aesthetics: Detailed UI design elements are assumed outside of the scope for this assignment.
4. External System Integration: Integration with external systems (other than bank communication) are not considered part of initial testing.
5. Performance Under High Load: Load testing for high-volume transactions might not be part of exploratory testing.

This exploratory testing plan is tailored to validate the ATM SUT V1.0's critical functionalities in a thorough yet flexible manner. It is designed to uncover a wide range of potential issues, ensuring that the system is robust, user-friendly, and aligns with the specified requirements, while efficiently managing testing resources.

**1. Card and PIN Validation**

1.  Test with valid card numbers (1 and 2) and correct PINs.
1.  Test with valid card numbers and incorrect PINs.
1.  Test with invalid card numbers (not 1 or 2) regardless of PIN.
1.  Test behavior after three consecutive incorrect PIN attempts for valid cards (card retention).

**2. Cash Withdrawal**

1.  Test cash withdrawals in multiples of $20 with valid card and PIN.
1.  Test withdrawal requests that exceed account balance.
1.  Verify bank approval process for each withdrawal transaction.

**3. Deposits**

1. Test deposit of envelopes with accurate amount entries.
1. Test deposit function with invalid card or PIN.
1. Test deposit without entering any amount or incorrect amounts.
1. Validate manual verification process post-deposit.

**4. Money Transfers**

1. Test transfers between linked accounts (checking to savings, savings to money market, etc.).
1. Test transfers with insufficient funds in the source account.
1. Test transfer functionality with invalid card or PIN.
1. Verify bank approval for each transfer transaction.

**5. Balance Check**

1. Verify balance display for various accounts with valid card and PIN.
1. Test balance inquiry with invalid card or PIN.
1. Check for real-time update in balance after transactions (withdrawal, deposit, transfer).

**6. Transaction Abortion**

1. Test the 'Cancel' key functionality during different transaction stages (withdrawal, deposit, transfer, balance inquiry).
1. Verify system response and state after transaction abortion.

**7. Receipt Generation**

1. Validate receipt content for different transactions (withdrawal, deposit, transfer).
1. Test printer functionality and error handling (e.g., paper jam, no paper).
1. Verify date, time, location, transaction type, accounts, amounts, and balances on the receipt.

**8. Operator Controls**

1. Test key-operated switch for starting and stopping the machine.
1. Verify system behavior when switched to "off" position (shutdown process).
1. Check system state and functionality upon restarting after shutdown.

**9. Internal Transaction Log**

1. Ensure logging of all transaction types (withdrawals, deposits, transfers, balance inquiries).
1. Validate log entries for system startup and shutdown.
1. Check for the inclusion of necessary details (except PIN) in log entries.

**10. Bank Communication**

1. Validate communication protocol for successful and failed transactions.
1. Test system response to different messages from the bank.
1. Ensure that the system communicates each transaction accurately to the bank.

**11. Software Failure Handling**

1. Close the ATM system while in the middle of a transaction to simulate hardware failure and check test system response.

# Comparison of exploratory and manual functional testing

## 1. **Manual Functional Testing:**

Ideal for confirming specific, known scenarios and essential in regression testing to ensure stability after changes.

### 1.1 Advantages

- Offers precise and comprehensive coverage based on specific test cases.
- Provides clear benchmarks for evaluating system performance.
- Serves as detailed documentation for future reference and training.

### 1.2 Limitations

- Tends to be time-intensive and labor-heavy.
- Limited to predefined scenarios, potentially missing out on edge cases.

## 2. **Exploratory Testing:**

Highly effective in discovering new, unexpected bugs and exploring system behavior in atypical situations. More efficient in situations where a complete test suite is not feasible, such as early development phases or with complex systems.

### 2.1 Advantages

- Allows for dynamic testing, uncovering unexpected bugs.
- Leverages tester intuition for in-depth analysis and insights.
- Particularly effective in complex or early development stages.

### 2.2 Limitations

- Might leave some areas under-tested, leading to gaps in coverage.
- Finding and replicating issues can be more challenging.

# Notes and discussion of the peer reviews of defect reports

The key talking points in our review sessions were based on the following:

- We strived for completeness and comprehensiveness of the reports. This meant that we reviewed that every work item stated which function was being tested, the description of the issue, the state of the system, steps to reproduce the bug, and the expected and actual results. We tried to keep the information concise to be able to quickly look through the report. 

- We all had to agree on the severity ratings assigned to defect. For example Work ID 5, was rated as Critical due to the fact that it was negatively impacting the system's functionality and had undesired effects that was a risk to the business.

- We all had to agree on the tags for consistency. The tags column used to indicate the testing phase and version makes the report easier to read. 

- We discussed the importance of regularly updating the defect status. For defects that are still active, such as Work Item 6 and others, we provide a Closing Comment to provide clarity on corrective actions taken and current status. 

We talked about lessons learned on how to properly document defects. The sessiosn helped us identify areas of improvement and ensured that all members had a clear understanding of defect lifecycle management process.


# How the pair testing was managed and team work/effort was divided

We used the suggested "pair testing" approach, which made use of one member conducting the testing while the other reviewed and analyzed the results. We split the pair testing in the following tasks where one member was in charge of executing the tests and the other was responsible for documentation.


### Card and PIN Validation
- Brandon and Mustayeen

### Cash Withdrawal
- Mevin and Kate

### Deposits
- Nur and Brandon

### Money Transfers
- Mustayeen and Mevin

### Balance Check
- Kate and Nur

### Transaction Abortion
- Brandon and Mevin

### Receipt Generation
- Mustayeen and Kate

### Operator Controls
- Mevin and Nur-Alhuda

### Internal Transaction Log
- Brandon and Kate

### Bank Communication
- Mustayeen and Nur-Alhuda

### Software Failure Handling
- Mevin and Brandon


We organized the division of tasks in the above format to ensure that every member got exposure to different test scenarios. After each pair testing session, we also discussed together as a group to ensure consistency of the defect reports. After all the tests have been completed, we organized our findings together where we went over the defect rpeort one last time. 

# Difficulties encountered, challenges overcome, and lessons learned

While navigating through this assignment, our team managed various tasks effectively and things generally progressed smoothly. We had trouble using Azure DevOps, which presented a learning curve and was a bit time consuming. Additionally, efficiently allocating tasks among team members was a challenge, impacting our overall productivity. Moving forward, we aim to familiarize ourselves more with Azure DevOps early in the process, focusing on enhancing task management and team collaboration for future projects.

This assignment was great as a learning exprience in software testing. It would have been beneficial to practice Azure or Jira in the lectures, however, the assignment encompasses system exploration, application of diverse testing techniques, and verification of issue resolutions in updated software versions. The assignment guidelines are straightforward, though we had some difficulty figuring out the format of the report (md file vs the Test Plan example provided). It was good to promote pair work as it further enriches the learning experience through collaboration. The documentation is user-friendly, featuring clear language and constructive feedback opportunities.

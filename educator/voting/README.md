## Overview

Instructors can setup a voting question for students to vote for some popular solutions of specific assessments.

## Content

- [Voting Workflow](#voting-workflow)
   - [Instructor](#instructor)
   - [Students](#students)
- [Voting XML](#contest-voting-xml)
- [Voting Guide](#voting-guide)
  - [Different Contest Types](#different-contest-types)
  - [Random Assignment of Entries](#random-assignment-of-entries)
  - [Valid vs Invalid Entries](#valid-vs-invalid-entries)
- [Leaderboard](#leaderboard)
## Voting Workflow

### Instructor

1. Upload a contest.xml in ground control

   Note that the backend **does not anonymize** students' answers, hence students should submit a standardized function header without their names for anonymity.
2. Once the contest has ended, upload the contest-voting.xml in ground control

   The vote assignment will be generated at the point of time of upload of contest-voting.xml (this is a possible future improvement that can be made)
3. Students can vote once the contest voting assessment is open, and the rolling leaderboard will compute the scores

   The rolling leaderboard will compute the scores of each student based on votes recieved and number of tokens in the student's answer. More information can be found in [Leaderboard](#leaderboard).

### Students

1. Students access the side contents to vote for their favorite entries. They can click on the card which will input the entry into the AssessmentEditor.
Students can then execute the program and view the contest entries to vote for.
![image](https://user-images.githubusercontent.com/51410656/120003514-67486080-c008-11eb-9e06-c585985937e9.png)

2. Once the student finalises the submission, the voting boxes are disabled and their votes are included in the leaderboard score tally.
![image](https://user-images.githubusercontent.com/51410656/120004034-e342a880-c008-11eb-9bf9-d6d3bffde054.png)

## Contest Voting XML

Similar to the creating an [assessment xml](educator/assessment/README.md) for programming and mcq questions, except that except that you need to declare the [PROBLEM](educator/assessment/README.md#problem) type as “voting” and include a VOTING tag `<VOTING assessment_number='??' />`.

### VOTING Attributes

| attribute | details |
| --------- | ------- |
| assessment_number | The assessment number of the **contest** (i.e. If a contest was uploaded with the number "C4", the assessment_number will be "C4"). Required. |

### Example of a contest voting xml:

```xml
<?xml version="1.0"?>
<CONTENT xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://128.199.210.247">

<!-- ***********************************************************************
**** Contest Voting #D7
************************************************************************ -->
<TASK
  kind="practical"
  coverimage="http://via.placeholder.com/350x150"
  number="D7"
  title="Beautiful Runes Contest Voting"
>
  <READING>Textbook Chapter 1</READING>

  <TEXT>
Now is the time to rank the most beautiful runes made by your peers!

You will be randomly assigned 10 runes to rank!
  </TEXT>

  <PROBLEMS>
    <PROBLEM type="voting" maxgrade="0" maxxp="100"> <!-- problem type is "voting"-->
      <TEXT>
You can now vote on the most beautiful runes made by your fellow students!
      </TEXT>
      <SNIPPET>
        <TEMPLATE>
Rank the beautiful runes!
        </TEMPLATE>
      </SNIPPET
      <VOTING assessment_number="C4"/> <!-- addditional Voting tag -->
    </PROBLEM>
  </PROBLEMS>

  <DEPLOYMENT interpreter="1">
  </DEPLOYMENT>

</TASK>
</CONTENT>
```

## Voting Guide

### Different Contest Types

### Random Assignment of Entries

### Valid vs Invalid Entries

## Leaderboard

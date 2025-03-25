# TICKET-101 validation

## Summary of the ticket

This ticket incudes following functionalites:
<li>Personal code validation</li>
<li>Loan amount validation</li>
<li>Loan period validation</li>
<li>Credit score calculation</li>
<li>Returns a decision</li>
<li>Returns a loan amount</li>
</br>
All tests have been passed.

## What the intern did well

<li>The front-end and back-end logic for validating personal code, loan amount, and loan period is correctly implemented.</li>
<li>User interface is intuitive and well-designed.</li>
<li>All errors are being handled properly.</li>
<li>Back-end logic for getting the credit modifier according to the personal code's last for digits is well-implemented, with correctly defined credit modifiers segments. </li>
<li>API request and response handling is done correctly with well-structured decision responses.</li>

## What could be improved

<li>The entire credit score calculation logic was missing and needed to be implemented.</li>
<li>Maximum and minimum loan periods were incorrect and had to be fixed.</li>
<li>Test cases didn't showcase edge cases properly and contained errors.</li>
<li>More test cases should be implemented.</li>

## Most important shortcoming of TICKET-101

The most critical problem was the absence of the entire credit score calculation logic. This led to all the loans being handed out incorrectly. This is a major shortcoming, since it is very important the loans are being granted correctly. The credit score is calculated according to the credit modifier, which is therefore used to either allow a certain amount of loan for a certain a period or not.
</br>

As of now the issue has been addressed and the credit score logic has been implemented. 

## What to do next

If there's extra time, the code should be reviewed for potential duplication, as well as check if best coding practices should be implemented. Performance testing could be done as well.

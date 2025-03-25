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

The front-end and back-end logic for the personal code, loan amount and loan period validation is correctly implemented. User interface is intuitive and nicely designed. All errors are being handled correctly.

</br>

Back-end logic for getting the credit modifier according to the personal code's last for digits is well-implemented as well as the credit modifiers segments. 

</br>

API request and response endpoints have been done correctly. Decision responses are done well.

## What could be improved

<li>The entire credit score calculation logic was missing and needed to be implemented.</li>
<li>Maximum and minimum loan periods were incorrect and had to be fixed.</li>
<li>Test cases didn't showcase edge cases and were done wrong.</li>

## Most important shortcoming of TICKET-101

The entire credit score calculation logic was missing, which means all the loans were handed out wrong. This is a major shortcoming, since it is very important the loans are being granted correctly. The credit score is calculated according to the credit modifier, which is therefore used to either allow a certain amount of loan for a certain a period or not.
</br>

As of now, the credit score logic has been fixed.

# InBank Backend Service

This service provides a REST API for calculating an approved loan amount and period for a customer. The loan amount is calculated based on the customer's credit modifier, which is determined by the last four digits of their ID code.

## Technologies Used
- Java 17
- Spring Boot
- [estonian-personal-code-validator:1.6](https://github.com/vladislavgoltjajev/java-personal-code)

## Requirements

- Java 17
- Gradle

## Installation

To install and run the service, please follow these steps:
1. Clone the repository.
2. Navigate to the root directory of the project.
3. Run `gradle build` to build the application.
4. Run `java -jar build/libs/inbank-backend-1.0.jar` to start the application

The default port is 8080.

## Endpoints

The application exposes a single endpoint:
### POST /loan/decision

The request body must contain the following fields:

- personalCode: The customer's personal ID code.
- loanAmount: The requested loan amount.
- loanPeriod: The requested loan period.

**Request example:**

```json
{
"personalCode": "50307172740",
"loanAmount": "5000",
"loanPeriod": "24"
}
```

The response body contains the following fields:

- loanAmount: The approved loan amount.
- loanPeriod: The approved loan period.
- errorMessage: An error message, if any.

**Response example:**

```json
{
"loanAmount": 2400,
"loanPeriod": 24,
"errorMessage": null
}
```

## Error Handling

The following error responses can be returned by the service:

- `400 Bad Request` - in case of an invalid input
    - `Invalid personal ID code!` - if the provided personal ID code is invalid
    - `Invalid loan amount!` - if the requested loan amount is invalid
    - `Invalid loan period!` - if the requested loan period is invalid
- `404 Not Found` - in case no valid loans can be found
    - `No valid loan found!` - if there is no valid loan found for the given ID code, loan amount, and loan period
- `500 Internal Server Error` - in case the server encounters an unexpected error while processing the request
    - `An unexpected error occurred` - if there is an unexpected error while processing the request

## Architecture

The service consists of two main classes:

- DecisionEngine: A service class that provides a method for calculating an approved loan amount and period for a customer.
- DecisionEngineController: A REST endpoint that handles requests for loan decisions.

<br/>

# ***TICKET-101 validation***

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

# ***TICKET-102 implementation***

Added functionalities:
<li>Age limit constants</li>
<li>Invalid age exception</li>
<li>Age verification functionality inside input verification functionality</li>
<li>Underaged and over the maximum age clients will not be able to apply for a loan</li>
<li>Frontend gives feedback when the loan was not given due to age constraints</li>
<li>Age verification tests</li>

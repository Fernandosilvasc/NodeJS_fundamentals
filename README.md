<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios-new.png" />

<h3 align="center">
  Challenge 05: NodeJs Fundamentals
</h3>

<p align="center">
 <img src="https://img.shields.io/static/v1?label=PRs&message=welcome&color=#FE7F2D&labelColor=#FE7F2D" alt="PRs welcome!" />

  <img alt="License" src="https://img.shields.io/static/v1?label=license&message=MIT&color=#FE7F2D&labelColor=#FE7F2D">
</p>


<p align="center">
  <a href="#rocket-about-the-challenge">About the challenge</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-licence">Licence</a>
</p>

## :rocket: About the challenge

In this challenge, it was necessary to create an application using Node.js and TypeScript, using the concepts of models, repositories and services!

Basically this application is to store incoming and outgoing financial transactions, which should allow the registration and listing of these transactions.

### Application Routes

This was requested through that challenge.

- **`POST / transactions`**: The route must receive` title`, `value` and` type` within the body of the request, with `type` being the type of the transaction, which must be` income` for entries ( deposits) and outcome for withdrawals (withdrawals). When registering a new transaction, it must be stored inside an object with the following format:

```json
{
  "id": "uuid",
  "title": "Paycheck",
  "value": 3000,
  "type": "income"
}
```

- **`GET / transactions`**: This route should return a listing with all the transactions that you have registered so far, together with the sum of entries, withdrawals and total credit. This route must return an object with the following format:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Paycheck",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freelance Project",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Bills",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Gamer Chair",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

**Tip**: Within balance, income is the sum of all transaction values with `type` income. The outcome is the sum of all transaction values with 'type` outcome, and the total is the value of' income - outcome '.

**Tip 2**: To sum up the values, you can use the function [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) to group transactions by the `type` property, so you will be able to add up all the values easily and get the return of` balance`.


### Tests Specification

To complete this challenge was necessary to follow these rules:

- **`should be able to create a new transaction`**: For this test to pass, your application must allow a transaction to be created, and return a json with the created transaction.

- **`should be able to list the transactions`**: In order for this test to pass, your application must allow an object containing all transactions to be returned together with the balance of income, outcome and total transactions that were created up to the time.

- **`should not be able to create outcome transaction without a valid balance`**: In order for this test to pass, your application must not allow a` outcome` transaction to exceed the total amount that the user has in cash, returning a response with HTTP 400 code and an error message in the following format: `{error: string}`

## :memo: Licence

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for more information.

---

👨🏻‍💻 - Made by Fernando Corrêa da Silva.

# Financial Calculators

## Introduction

**Financial Calculators API** provides a set of high-level financial formulas such as loan payments, rate, present value, car payments, and much more... with amortization schedules....

## Authentication

The URL you need to use is the following: `https://financial-calculators.p.rapidapi.com/`
The API requires the headers listed below:

- **`x-rapidapi-host`**: `financial-calculators.p.rapidapi.com`
- **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/financial-calculators/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

## Endpoints

The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

### Loan Calculators

#### 1. **`GET /homeloan`**

- **Description**: Retrieves the Home loan with Monthly Amortization i.e: How much will be my monthly payment on a house that cost $100000 with 20% as a down payment, with 5% interest rate and term of the loan is 30 years? rate=5 loant=30 hvalue=100000 downpayment=20

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The term of the loan in years               | Yes      |
| `hvalue`        | number | -       | The house value                             | Yes      |
| `downpayment`   | number | -       | The down payment percentage                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/homeloan?rate=5&loant=30&hvalue=100000&downpayment=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "downpayment": 20000,
    "loan_amount": 80000,
    "monthly_payment": 429.46,
    "number_month_to_pay": 360,
    "total_payments": 154604.63,
    "total_interest": 74604.63,
    "amortization": [
      {
        "month": {
          "month": 1,
          "interest": 333.33,
          "principal": 96.12,
          "beginning_balance": 80000,
          "ending_balance": 79903.88
        }
      },
      {
        "month": {
          "month": 2,
          "interest": 332.93,
          "principal": 96.52,
          "beginning_balance": 79903.88,
          "ending_balance": 79807.36
        }
      },
      {
        "month": {
          "month": 3,
          ...
```

#### 2. **`GET /carloan`**

- **Description**: Retrieves the Home loan with Monthly Amortization i.e: How much will be my monthly payment on a car that cost $25000 with 20% as a down payment, with 5% interest rate and term of the loan is 10 years? rate=5 loant=10 cprice=25000 downpayment=20

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The term of the loan in years               | Yes      |
| `cprice`        | number | -       | The cartvalue                               | Yes      |
| `downpayment`   | number | -       | The down payment percentage                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/carloan?rate=5&loant=10&cprice=25000&downpayment=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "downpayment": 5000,
    "loan_amount": 20000,
    "monthly_payment": 212.13,
    "number_month_to_pay": 120,
    "total_payments": 25455.72,
    "total_interest": 5455.72,
    "amortization": [
      {
        "month": {
          "month": 1,
          "interest": 83.33,
          "principal": 128.8,
          "beginning_balance": 20000,
          "ending_balance": 19871.2
        }
      },
      {
        "month": {
          "month": 2,
          "interest": 82.8,
          "principal": 129.33,
          "beginning_balance": 19871.2,
          "ending_balance": 19741.87
        }
      },
      {
        "month": {
          "month": 3,
          ...
```

#### 3. **`GET /carloanyear`**

- **Description**: Retrieves the Home loan with Yearly Amortization i.e: How much will be my monthly payment on a car that cost $25000 with 20% as a down payment, with 5% interest rate and term of the loan is 10 years? rate=5 loant=10 cprice=25000 downpayment=20

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The term of the loan in years               | Yes      |
| `cprice`        | number | -       | The cartvalue                               | Yes      |
| `downpayment`   | number | -       | The down payment percentage                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/carloanyear?rate=5&loant=10&cprice=25000&downpayment=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "downpayment": 5000,
    "loan_amount": 20000,
    "monthly_payment": 212.13,
    "number_month_to_pay": 120,
    "total_payments": 25455.72,
    "total_interest": 5455.72,
    "amortization": [
      {
        "year": {
          "year": 1,
          "interest_year": 964.08,
          "principal_year": 1581.49,
          "beginning_balance_year": 20000,
          "ending_balance": 18418.51
        }
      },
      {
        "year": {
          "year": 2,
          "interest_year": 883.17,
          "principal_year": 1662.4,
          "beginning_balance_year": 18418.51,
          "ending_balance": 16756.11
        }
      },
      {
        "year": {
          "year": 3,
          ...
```

#### 4. **`GET /homeloanyear`**

- **Description**: Retrieves the Home loan with Yearly Amortization i.e: How much will be my monthly payment on a house that cost $100000 with 20% as a down payment, with 5% interest rate and term of the loan is 30 years? rate=5 loant=30 hvalue=100000 downpayment=20

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The term of the loan in years               | Yes      |
| `hvalue`        | number | -       | The house value                             | Yes      |
| `downpayment`   | number | -       | The down payment percentage                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/homeloanyear?rate=5&loant=30&hvalue=30&downpayment=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "downpayment": 6,
    "loan_amount": 24,
    "monthly_payment": 0.13,
    "number_month_to_pay": 360,
    "total_payments": 46.38,
    "total_interest": 22.38,
    "amortization": [
      {
        "year": {
          "year": 1,
          "interest_year": 964.08,
          "principal_year": 1581.49,
          "beginning_balance_year": 20000,
          "ending_balance": 18418.51
        }
      },
      {
        "year": {
          "year": 2,
          "interest_year": 883.17,
          "principal_year": 1662.4,
          "beginning_balance_year": 18418.51,
          "ending_balance": 16756.11
        }
      },
      {
        "year": {
          "year": 3,
          ...
```

### Payments

#### 1. **`GET /pmt`**

- **Description**: Retrieves the monthly payment on a Loan. i.e: - What is the monthly payment needed to pay off a $100,000 loan in 10 years at an annual interest rate of 2.5%? rate=0.025 nper=10 pv=100000.

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `nper`          | number | -       | The number of years                         | Yes      |
| `pv`            | number | -       | The loan total value                        | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/pmt?rate=0.025&nper=10&pv=100000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "0.025",
    "nper": "10",
    "pv": "100000",
    "result": "942.70"
  }
]
```

#### 2. **`GET /pv`**

- **Description**: Retrieves the Present Value i.e: -> What is the present value (e.g., the initial investment) of an investment that needs to total $20,000 after 10 years of saving $100 every month? Assume the interest rate is 7% (annually) compounded monthly. rate=0.07 nper=10 pmt=100 fv=20000

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `nper`          | number | -       | The number of years                         | Yes      |
| `pmt`           | number | -       | The monthly investment value                | Yes      |
| `fv`            | number | -       | The total savings objective                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/pv?rate=0.07&nper=10&pmt=100&fv=20000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "0.07",
    "nper": "10",
    "pmt": "100",
    "fv": "20000",
    "result": "1339.29"
  }
]
```

#### 3. **`GET /pp`**

- **Description**: Retrieves how long it takes to recover the initial cost of an investment based on projected cash flows.

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `nperiods`      | number | -       | The number of periods                       | Yes      |
| `cflow`         | string | -       | The cash flows expected for each period     | Yes      |

Note: If the cash flows are even (the same amount each period), set nperiods to 0. For uneven cash flows (varying amounts each period), set nperiods to the number of projected periods. The first element of cflow must be the initial investment and a negative number. cflow values must be seperated by commas (ex: `-50,10,13,16,19,22`)

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/pp?nperiods=5&cflow=-50%2C10%2C13%2C16%2C19%2C22', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "number_periods": "5",
    "cashflow": [
      -50,
      10,
      13,
      16,
      19,
      22
    ],
    "result": "3.42"
  }
]
```

#### 4. **`GET /roi`**

- **Description**: Retrieves the bottom line return of any investment (ROI).

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `binvest`       | number | -       | The initial investment                      | Yes      |
| `earnings`      | number | -       | The total earnings of the investment        | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/roi?binvest=55000&earnings=60000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "initial_investiment": "55000",
    "earnings": "60000",
    "result": "9.09"
  }
]
```

### Interest

#### 1. **`GET /amortizationcalc`**

- **Description**: Retrieves the Principal and Interest payment calculation with Monthly Amortization Schedule.

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The number of years                         | Yes      |
| `lamount`       | number | -       | The loan total value                        | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/amortizationcalc?rate=10&loant=1&lamount=5000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "monthly_payment": 439.58,
    "number_month_to_pay": 12,
    "total_payments": 5274.95,
    "total_interest": 274.95,
    "amortization": [
      {
        "month": {
          "month": 1,
          "interest": 41.67,
          "principal": 397.91,
          "beginning_balance": 5000,
          "ending_balance": 4602.09
        }
      },
      {
        "month": {
          "month": 2,
          "interest": 38.35,
          "principal": 401.23,
          "beginning_balance": 4602.09,
          "ending_balance": 4200.86
        }
      },
      {
        "month": {
          "month": 3,
          "interest": 35.01,
          "principal": 404.57,
          ...
```

#### 2. **`GET /amortizationcalcyear`**

- **Description**: Retrieves the Principal and Interest payment calculation with yearly Amortization Schedule

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `loant`         | number | -       | The number of years                         | Yes      |
| `lamount`       | number | -       | The loan total value                        | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/amortizationcalcyear?rate=10&loant=1&lamount=5000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "monthly_payment": 439.58,
    "years_to_pay": 1,
    "number_month_to_pay": 12,
    "total_payments": "5274.95",
    "total_interest": 274.95,
    "amortization": [
      {
        "year": {
          "year": 1,
          "interest_year": 274.95,
          "principal_year": 5000,
          "beginning_balance_year": 5000,
          "ending_balance": 0
        }
      }
    ]
  }
]
```

#### 3. **`GET /rate`**

- **Description**: Retrieves  the interest rate for a loan based on provided parameters.

| Query Parameter | Type   | Default | Description                                  | Required |
|-----------------|--------|---------|----------------------------------------------|----------|
| `pv`            | number | -       | The loan total value                         | Yes      |
| `nper`          | number | -       | The loan term in years                       | Yes      |
| `pmt`           | number | -       | The monthly payment value                    | Yes      |
| `fv`            | number | -       | The value of the loan at the end of the term | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/rate?pv=8000&nper=5&pmt=152.5&fv=0', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "pv": "8000",
    "nper": "5",
    "pmt": "152.5",
    "fv": "0",
    "monthly_rate": "0.45",
    "yearly_rate": 5.4
  }
]
```

#### 4. **`GET /ci`**

- **Description**: Retrieves the interest calculated on the initial principal and also on the accumulated interest of previous periods of a deposit or loan (Compound Interest).

| Query Parameter | Type   | Default | Description                                 | Required |
|-----------------|--------|---------|---------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                           | Yes      |
| `cperiod`       | number | -       | The compoundings per period                 | Yes      |
| `principal`     | number | -       | The initial principal value                 | Yes      |
| `nperiods`      | number | -       | The number of periods                       | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/ci?rate=4.3&cperiod=4&principal=1500&nperiods=6', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "4.3",
    "compound_periods": "4",
    "principal": "1500",
    "number_periods": "6",
    "result": "1938.84"
  }
]
```

### Extras

#### 1. **`GET /fv`**

- **Description**: Retrieves the Future Value.

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `rate`          | number | -       | The annual interest rate (decimal)               | Yes      |
| `nper`          | number | -       | The number of years                              | Yes      |
| `pmt`           | number | -       | The additional monthly saving (must be negative) | Yes      |
| `pv`            | number | -       | The intial value                                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/fv?rate=0.07&nper=30&pmt=-100&pv=1000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "0.07",
    "nper": "30",
    "pmt": "-100",
    "pv": "1000",
    "result": "130113.60"
  }
]
```

#### 2. **`GET /nper`**

- **Description**: Retrieves the number of periods (months) needed to pay a loan.

| Query Parameter | Type   | Default | Description                                  | Required |
|-----------------|--------|---------|----------------------------------------------|----------|
| `rate`          | number | -       | The annual interest rate (decimal)           | Yes      |
| `pmt`           | number | -       | The monthly payment                          | Yes      |
| `pv`            | number | -       | The loan total value                         | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/nper?rate=0.03&pmt=500&pv=10000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "0.03",
    "pmt": "500",
    "pv": "10000",
    "result": 20
  }
]
```

#### 3. **`GET /irr`**

- **Description**: Retrieves the internal rate of return for a series of cash flows.

| Query Parameter | Type   | Default | Description                                  | Required |
|-----------------|--------|---------|----------------------------------------------|----------|
| `cflow`         | number | -       | The initial investment (must be negative)    | Yes      |
| `iinvest`       | string | -       | The cash flows expected for each period      | Yes      |

Note: `iinvest` values must be seperated by commas (ex: `500,500,500,500`)

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/irr?cflow=1500&iinvest=500%2C500%2C500%2C500', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "Investiments": "-1500,500,500,500,500",
    "result": "12.59"
  }
]
```

#### 4. **`GET /cagr`**

- **Description**: Retrieves the year-over-year growth rate of an investment over a specified period of time (Compound Annual Growth Rate).

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `bvalue`        | number | -       | The initial value of the investment              | Yes      |
| `evalue`        | number | -       | The final value of the investment                | Yes      |
| `nperiods`      | number | -       | The number of periods                            | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/cagr?bvalue=10000&evalue=19500&nperiods=3', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "beginning_value": "10000",
    "ending_value": "19500",
    "number_periods": "3",
    "result": "24.93"
  }
]
```

#### 5. **`GET /df`**

- **Description**: Retrieves the factor by which a future cash flow must be multiplied in order to obtain the present value (Discount Factor).

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                                | Yes      |
| `nperiods`      | number | -       | The number of periods                            | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/df?rate=10&nperiods=6', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "10",
    "number_periods": "6",
    "result": [
      1,
      0.91,
      0.827,
      0.752,
      0.684
    ]
  }
]
```

#### 6. **`GET /lr`**

- **Description**: Retrieves the financial leverage of a company or individual to get an idea of the methods of financing or to measure ability to meet financial obligations (Leverage Ratio).

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `tliability`    | number | -       | The total liabilities value                      | Yes      |
| `tdebts`        | number | -       | The total debt value                             | Yes      |
| `tincome`       | number | -       | The total income value                           | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/lr?tliability=25&tdebts=10&tincome=20', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "total_liability": "25",
    "total_debts": "10",
    "total_income": "20",
    "result": 1.75
  }
]
```

#### 7. **`GET /npv`**

- **Description**: Retrieves the Net Present Value (NPV) which compares the money received in the future to an amount of money received today, while accounting for time and interest [through the discount rate]. It's based on the principal of time value of money (TVM), which explains how time affects monetary value.

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                                | Yes      |
| `cflow`         | string | -       | The cash flows expected for each period          | Yes      |
| `iinvest`       | number | -       | The initial investment                           | Yes      |

Note: cflow values must be separated by commas (ex: `200000,300000,200000`)

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/npv?rate=10&cflow=200000%2C300000%2C200000&iinvest=500000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "10",
    "initial_investiment": "500000",
    "cashflow": [
      200000,
      300000,
      200000
    ],
    "result": 80015.03
  }
]
```

#### 8. **`GET /pi`**

- **Description**: Retrieves the profitability Index.

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                                | Yes      |
| `iinvest`       | number | -       | The initial investment                           | Yes      |
| `cflow`         | string | -       | The cash flows expected for each period          | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/pi?rate=10&iinvest=40000&cflow=18000%2C12000%2C10000%2C9000%2C6000', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "10",
    "initial_investiment": "40000",
    "cashflow": [
      18000,
      12000,
      10000,
      9000,
      6000
    ],
    "result": "1.09"
  }
]
```

#### 9. **`GET /r72`**

- **Description**: Retrieves the interest rate, you divide the compound return into 72.

| Query Parameter | Type   | Default | Description                                      | Required |
|-----------------|--------|---------|--------------------------------------------------|----------|
| `rate`          | number | -       | The interest rate                                | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/r72?rate=10', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "rate": "10",
    "result": "7.20"
  }
]
```

#### 10. **`GET /wacc`**

- **Description**: Retrieves the rate that a company is expected to pay on average to all its security holders to finance its assets (Weighted Average Cost of Capital).

| Query Parameter | Type   | Default | Description                                  | Required |
|-----------------|--------|---------|----------------------------------------------|----------|
| `mvaluee`       | number | -       | The market value of equity                   | Yes      |
| `mvalued`       | number | -       | The market value of debt                     | Yes      |
| `cequity`       | number | -       | The cost of equity                           | Yes      |
| `cdebt`         | number | -       | The cost of debt                             | Yes      |
| `trate`         | number | -       | The tax rate                                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/wacc?mvaluee=600000&mvalued=400000&cequity=6&cdebt=5&trate=35', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "market_value_equity": "600000",
    "market_value_debt": "400000",
    "cost_equity": "6",
    "cost_debt": "5",
    "tax_rate": "35",
    "result": "4.90"
  }
]
```

#### 11. **`GET /iar`**

- **Description**: Retrieves investment return taking into account the time period's inflation rate.

| Query Parameter | Type   | Default | Description                                  | Required |
|-----------------|--------|---------|----------------------------------------------|----------|
| `ireturn`       | number | -       | The investment return (decimal)              | Yes      |
| `irate`         | number | -       | The inflation rate (decimal)                 | Yes      |

Example request:

```javascript
fetch('https://financial-calculators.p.rapidapi.com/iar?ireturn=0.08&irate=0.03', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'financial-calculators.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "investiment_return": "0.08",
    "inflation_rate": "0.03",
    "result": "4.85"
  }
]
```

## Error Handling

The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |

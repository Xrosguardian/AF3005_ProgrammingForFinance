# AF3005_ProgrammingForFinance
A repository for Assignments and projects made in Programming for finance course at FAST NUCES ISB Campus
# Smart Financial Management System - Implementation Details

This project implements a Smart Financial Management System using Python and interactive elements powered by ipywidgets. Data visualization is achieved using matplotlib.pyplot. It is broken down into five parts:
## Part 1: Loan Eligibility & Interest Rate Calculation

### Functionality: This part assesses customer eligibility for loans based on employment status, income, and credit score. It then calculates the applicable interest rate or rejects the loan application.

### Implementation:

    Input: Utilizes ipywidgets to create interactive input elements:
        Dropdown for employment status (Employed, Unemployed).
        IntText for monthly income (PKR).
        IntSlider for credit score (300-850).
    Logic: Employs if-elif-else statements for decision-making:
        if employment.value == 'Unemployed':: Immediately rejects if unemployed.
        if income.value < 50000:: Rejects if income is below PKR 50,000.
        if credit_score.value >= 750:: Approves with a 5% interest rate for credit scores 750 or above.
        elif 650 <= credit_score.value < 750:: Approves with an 8% interest rate for credit scores between 650 and 749.
        else:: Rejects if credit score is below 650.
    Output: Prints the loan decision and interest rate (if applicable) to the output area using print() statements within an Output widget.

## Part 2: Investment Risk Assessment

### Functionality: This part analyzes a portfolio of stocks based on their returns and classifies the risk level as High, Medium, or Low.

### Implementation:

    Input: Employs ipywidgets to allow users to input a comma-separated list of stock returns using a Text widget.
    Logic:
        Parses the input string using split(','), converts values to floats using float(), and handles potential errors with try-except blocks.
        Iterates through the list of returns using a for loop.
        Classifies risk using if-elif conditions:
            if any(r < 0 for r in returns):: High Risk if any return is negative.
            elif all(r >= 5 for r in returns):: Low Risk if all returns are 5% or above.
            elif any(0 < r < 5 for r in returns):: Medium Risk if there's a mix of returns below and above 5%.
    Output: Prints the risk classification to the output area using print() statements within an Output widget.

## Part 3: Loan Repayment Tracker

### Functionality: This part simulates loan repayment by tracking the remaining balance after each monthly payment.

### Implementation:

    Input: Uses ipywidgets for interactive input:
        IntText for the total loan amount.
        IntText for the monthly payment amount.
    Logic:
        Initializes the loan balance and uses a while loop to simulate payments until the balance reaches zero.
        Inside the loop, it deducts the payment, prints the remaining balance, and updates the month counter.
    Output:
        Uses print() statements to display the repayment progress sequentially.
        Utilizes matplotlib.pyplot to create a line plot showing the balance over time. This involves creating a figure and axes (fig, ax = plt.subplots()), plotting the data (ax.plot()), setting labels and titles (ax.set_title(), ax.set_xlabel(), etc.), and displaying the plot (plt.show()).
        Provides a summary of the loan details using print() statements.

## Part 4: Stock Price Monitoring and Trading Strategy

### Functionality: This part tracks stock prices over time and triggers an alert when the price reaches a target value. It also handles missing stock data.

### Implementation:

    Input: Employs ipywidgets to collect user input:
        IntText for the target price.
        Text widget for a comma-separated list of stock prices, allowing for "None" or empty values to represent missing data.
    Logic:
        Parses the input string, handles missing data using continue within a loop, and converts valid prices to floats.
        Iterates through the prices, checking if the target price is reached. If so, it uses break to stop tracking.
    Output:
        Uses matplotlib.pyplot to plot the stock price history. It highlights the trigger point (if any) using ax.scatter() and adds a horizontal line for the target price using ax.axhline().
        Prints an alert message if the trigger condition is met, indicating the day it occurred.

## Part 5: Currency Exchange Rate Tracker

### Functionality: This part simulates the daily change in the currency exchange rate between PKR and USD, starting at a specified rate and increasing by 1 PKR per day until it reaches a target rate.

### Implementation:

    Input: Utilizes ipywidgets to obtain the starting exchange rate using a FloatText widget.
    Logic:
        Initializes the current rate and uses a while loop to simulate daily changes until the target rate (300 PKR/USD) is reached.
        Inside the loop, it prints the current rate for each day and increments the rate by 1.
    Output:
        Uses print() statements to display the exchange rate simulation results.
        Employs matplotlib.pyplot to create a line plot showing the exchange rate over time. This includes plotting the data, adding a horizontal line for the target rate, and setting labels and titles.
        Provides a summary of the simulation parameters and results using print() statements.

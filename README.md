# Console-finances
This JavaScript code analyses financial data represented in the finances array. It calculates and prints key financial metrics, including the total number of months, total profit, average monthly change, and the greatest increase and decrease in profits.

Code Overview
1. Total Number of Months
javascript
Copy code
var totalMonths = finances.length;
console.log("Total number of months: " + totalMonths);
2. Financial Metrics Calculation
javascript
Copy code
var change = 0; 
var totalChange = 0;
var average = 0;
var increase = 0;
var decrease = finances[0][1];

var netProfit = finances[0][1];
var previous = netProfit;

for (let i = 1; i < finances.length; i++) {
  netProfit = netProfit + finances[i][1];
  change = finances[i][1] - previous;

  // Update greatest increase
  if (increase > change) {
    var greatestIncrease = increase;
  } else {
    increase = change;
  }

  totalChange = totalChange + change;
  previous = finances[i][1];

  // Update greatest decrease
  if (decrease < change) {
    var greatestDecrease = decrease;
  } else {
    decrease = change;
  }
}

average = totalChange / (finances.length - 1);
3. Output Results
javascript
Copy code
console.log("Total: $" + netProfit);
console.log("Average Change: $" + Math.round((average * 100))/100);
console.log("Greatest Increase: $" + greatestIncrease);
console.log("Greatest Decrease: $" + greatestDecrease);
Explanation
Total Number of Months: Calculates and logs the total number of months in the dataset.

Financial Metrics Calculation: Iterates through the financial data to calculate key metrics:

Net Profit: Calculates the total profit over the entire period.
Monthly Change: Calculates the change in profit each month and updates the greatest increase and decrease.
Output Results: Displays the calculated financial metrics in the console.

Notes
The code assumes the dataset is ordered chronologically.
The greatest increase and decrease represent the maximum positive and negative changes in profit, respectively.

I want to thank my pod as they were a great help but especially my team mate Alexandru Pandelea who particularly helped my group. 


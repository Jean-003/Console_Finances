#Obective

This project created a tool utilising Javascript for analysing the financial records of a company. The primary objective of this project involved providing a comprehensive analysis of a company's financial data, enabling stakeholders to gain insights into the company's financial performance.

##The URL of the deployed application:
http://127.0.0.1:5500/index.html


##The URL of the GitHub repository that contains the code:

https://github.com/Jean-003/Console_Finances

##Usage
To view the financial analysis results summary:
Open the Chrome DevTools by pressing Control+Shift+I (Windows) or Command+Option+I (macOS). This opens a console panel to the side of the webpage or below the webapage in the browser where you can find an analysis of results.

##Screenshot
![Image displaying the console]   
(Images\Screenshot 2024-02-16 165930.png)

![Image displaying the console in the browser]

(https://github.com/Jean-003/Console_Finances/assets/152238337/8454d36d-1952-42ad-a45d-04ffd8cfd0b2)

##Licences
None


##_References_

Financial Data was provided by EdX.

The following JavaScript starter code was also supplied by EdX:

// Initialize variables to store the required information
let totalMonths = 0;
let netTotal = 0;
let totalChange = 0;
let greatestIncrease = { date: '', amount: 0 };
let greatestDecrease = { date: '', amount: 0 };

// Iterate through the financial data
for (let i = 0; i < financialData.length; i++) {
  const currentMonth = financialData[i][0];
  const currentAmount = financialData[i][1];

  // Increment total months and net total
  totalMonths++;
  netTotal += currentAmount;

  // Calculate change in Profit/Losses
  if (i > 0) {
    const change = currentAmount - financialData[i - 1][1];
    totalChange += change;

    // Update greatest increase and decrease
    if (change > greatestIncrease.amount) {
      greatestIncrease.date = currentMonth;
      greatestIncrease.amount = change;
    }

    if (change < greatestDecrease.amount) {
      greatestDecrease.date = currentMonth;
      greatestDecrease.amount = change;
    }
  }
}

// Calculate the average change
const averageChange = totalChange / (totalMonths - 1);

// Display the results
console.log('Total Months:', totalMonths);
console.log('Net Total Profit/Losses:', netTotal);
console.log('Average Change:', averageChange);
console.log('Greatest Increase in Profits:', greatestIncrease.date, greatestIncrease.amount);
console.log('Greatest Decrease in Profits:', greatestDecrease.date, greatestDecrease.amount);

# Web Application Performance Testing Guide

This guide provides step-by-step instructions on how to execute a performance testing plan for a web application using Blazemeter and Apache JMeter. We will use Blazemeter to record user actions and generate a `.jmx` file, which we will then import into JMeter to execute performance tests and generate reports.

---

## Prerequisites

1. **Blazemeter Account**: Set up an account on [Blazemeter](https://www.blazemeter.com/).
2. **Blazemeter Plugin**: Install the Blazemeter plugin in your browser.
3. **Apache JMeter**: Download and install [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi).

---

## Steps to Execute Performance Test

### 1. Set Up Blazemeter and Sign In

1. Go to [Blazemeter](https://www.blazemeter.com/) and sign up or log in to your account.
2. Once logged in, go to your dashboard to get ready for recording.

### 2. Install the Blazemeter Plugin

1. Install the Blazemeter plugin for your browser (available for Chrome and Firefox).
2. After installation, log in to the plugin using your Blazemeter account credentials.

### 3. Record Actions on the Web Application

1. Go to your web application and click on the Blazemeter plugin icon in your browser.
2. Start a new recording session by clicking the **Start Recording** button in the plugin.
3. Perform the actions on your web application that you want to test (e.g., login, search, add to cart).
4. When you've completed the actions, stop the recording by clicking the **Stop** button in the plugin.

### 4. Convert Recording to JMX File

1. After stopping the recording, go to the Blazemeter plugin and choose the option to export your recording as a `.jmx` file.
2. Save the `.jmx` file to your local system.

### 5. Install Apache JMeter

1. Download Apache JMeter from the [JMeter website](https://jmeter.apache.org/download_jmeter.cgi).
2. Extract the downloaded file to a location on your computer.
3. Navigate to the extracted folder and open the `bin` directory.
4. Launch JMeter by running the `jmeter.bat` file (Windows) or `jmeter` script (MacOS/Linux).

### 6. Import JMX File and Execute Performance Test

1. In JMeter, go to **File** > **Open** and select the `.jmx` file you saved from Blazemeter.
2. Review the test plan structure and modify parameters as needed (e.g., number of users, ramp-up time).
3. Start the test by clicking on the **Start** button (green play icon) on the JMeter toolbar.

### 7. Generate Report

1. Once the test execution completes, you can view the results in the **Listeners** (e.g., Summary Report, Graph Results) that were added to the test plan.
2. Save the test results by right-clicking on the listener and selecting **Save Table Data** (for summary) or **Save Graph** (for visual data).
3. Export the report as needed for further analysis and documentation.

---

## Additional Tips

- **Customizing the Test Plan**: Modify the parameters in JMeter (e.g., thread count, loop count) to simulate different levels of load.
- **Error Handling**: Check for errors in JMeter’s result listeners to diagnose and fix any performance issues.

With this setup, you can conduct performance testing for your web application and evaluate the application’s behavior under various load conditions.


## Multi-Currency Payment System Test Execution with Cypress

This document provides instructions on setting up and executing a test plan for a multi-currency payment system using Cypress. The focus is on validating functionality, accuracy, and usability for various currencies (Naira, US Dollar, British Pound, and Euro) in the payment workflow.

## Prerequisites
1. **Node.js** (version 12 or higher)
Ensure Node.js is installed. Check installation:
node -v

2. **Cypress**
Install Cypress globally or locally within the project directory.

3. **Git**
Clone the repository for this test suite.

4. **Multi-Currency Payment System Environment**
Ensure the application’s test environment is set up with access to the multi-currency functionality.

## Getting Started
1. **Clone the Repository**
   git clone https://github.com/your-username/multi-currency-payment-system-tests.git
   cd multi-currency-payment-system-tests

2. **Install Dependencies**
Navigate to the project directory and install the necessary packages:

npm install

### **Test Execution Document for Multi-Currency Payment System**

---

**Project Name:** Multi-Currency Payment System  
**Test Plan Document Version:** 1.0  
**Prepared By:** [Your Name]  
**Date:** [Today's Date]

---

### **1. Introduction**

This document outlines the steps for executing and testing the multi-currency payment system. The goal is to verify the system’s functionality for handling payments in various currencies (Naira, US Dollar, British Pound, Euro) and ensure that it performs as expected under different transaction scenarios.

---

### **2. Test Execution Overview**

**Objective:**  
To ensure the system handles multi-currency transactions properly, with accurate currency conversion, processing, and display. This includes testing currency selection, transaction processing, error handling, and reporting.

### **3. Test Environment Setup**

Before executing the tests, ensure the following setup steps are completed:

1. **Test Environment Configuration:**
   - Ensure the test environment has access to real-time exchange rates or mock data for currency conversion.
   - Set up the required test accounts, both user and administrator, with different currency preferences.
   - Confirm that the payment gateway is connected to the test environment and supports multi-currency transactions.

2. **Tools Configuration:**
   - **API Testing Tool:** K6 configured to simulate currency-related API requests.
   - **Performance Testing Tools:** Blazemeter or JMeter for load testing the payment system.
   - **Manual Testing Tools:** Browser with developer tools for visual checks and verification.
   - **Automation Tools:** Selenium for automated UI tests and transaction simulation.

### **4. Test Execution Procedure**

#### **4.1. Currency Selection and Conversion Testing**

- **Test Case 1: Currency Selection**
  1. Open the payment checkout page.
  2. Select one of the supported currencies: Naira, USD, GBP, or EUR.
  3. Verify that the selected currency appears correctly on the payment summary.
  4. Ensure that the corresponding amount for the selected currency is shown (e.g., 5000 NGN, 20 USD, etc.).
  5. **Expected Result:** The correct currency symbol and format are displayed.

- **Test Case 2: Conversion Accuracy**
  1. Add an item to the cart.
  2. Choose a currency (e.g., USD) for payment.
  3. Convert the payment from one currency to another (e.g., USD to NGN).
  4. Verify that the conversion rate applied is accurate based on real-time exchange rates.
  5. **Expected Result:** The converted amount is correct based on the latest exchange rate.

#### **4.2. Payment Processing Testing**

- **Test Case 3: Payment in Naira**
  1. Select Naira (NGN) as the payment currency.
  2. Enter payment details (e.g., credit card information).
  3. Submit the payment request.
  4. **Expected Result:** The payment should be processed successfully in Naira, and the correct amount is deducted.

- **Test Case 4: Payment in USD**
  1. Select USD as the payment currency.
  2. Enter payment details.
  3. Submit the payment request.
  4. **Expected Result:** The payment should be processed successfully in USD, and the correct amount is deducted.

- **Test Case 5: Payment in GBP**
  1. Select GBP as the payment currency.
  2. Enter payment details.
  3. Submit the payment request.
  4. **Expected Result:** The payment should be processed successfully in GBP.

- **Test Case 6: Payment in EUR**
  1. Select EUR as the payment currency.
  2. Enter payment details.
  3. Submit the payment request.
  4. **Expected Result:** The payment should be processed successfully in EUR.

- **Test Case 7: Multi-Currency Payment Gateway Integration**
  1. Perform payments in all four currencies (NGN, USD, GBP, EUR).
  2. Validate that the payment gateway successfully processes payments in all currencies.
  3. **Expected Result:** All payments should be processed without errors and match the expected values in respective currencies.

#### **4.3. Currency Formatting and Display**

- **Test Case 8: Currency Formatting**
  1. Perform a test transaction in each of the supported currencies.
  2. Verify that each currency displays its symbol and decimal points correctly (e.g., USD with 2 decimals, NGN with no decimals).
  3. **Expected Result:** Currency values are formatted properly according to the local conventions for each currency.

- **Test Case 9: Conversion Rate Display**
  1. At the checkout page, display the conversion rate from one currency to another (e.g., NGN to USD).
  2. Verify that the conversion rate is correct and clearly shown.
  3. **Expected Result:** The conversion rate is visible to the user, and the rate is accurate.

#### **4.4. Error Handling Testing**

- **Test Case 10: Unsupported Currency Error**
  1. Attempt to process a payment in an unsupported currency.
  2. **Expected Result:** The system should display an error message indicating that the currency is not supported and prevent the transaction from processing.

- **Test Case 11: Exchange Rate Unavailability**
  1. Simulate a scenario where the exchange rate is unavailable.
  2. **Expected Result:** The system should either fail gracefully or provide a message to the user explaining the issue (e.g., “Exchange rate unavailable at this time”).

#### **4.5. Transaction Logging and Reporting**

- **Test Case 12: Transaction Logs**
  1. Verify that every transaction in each currency is logged correctly in the system.
  2. Confirm that the transaction log contains details such as the currency used, conversion rate (if applicable), transaction amount, and user ID.
  3. **Expected Result:** The transaction logs should accurately reflect the currency and amount, with proper timestamping and conversion details.

- **Test Case 13: Reporting for Multi-Currency Transactions**
  1. Generate a report that includes transactions in multiple currencies.
  2. Verify that the report correctly totals the amounts in their respective currencies.
  3. **Expected Result:** The report should include all transaction details, showing the correct totals for each currency type.

---

### **5. Performance Testing**

To validate the scalability and performance of the multi-currency payment system under different loads, perform the following tests using **Blazemeter** or **JMeter**:

- **Test Case 14: Load Testing**
  1. Simulate 500 concurrent users performing payment transactions in all four currencies.
  2. Measure system response times, throughput, and error rates.
  3. **Expected Result:** The system should handle the load with acceptable response times and minimal errors.

- **Test Case 15: Stress Testing**
  1. Gradually increase the number of concurrent users to 2000 and simulate payments in all currencies.
  2. Monitor server performance (CPU, memory, and network).
  3. **Expected Result:** The system should degrade gracefully, showing no critical errors or crashes.

- **Test Case 16: Endurance Testing**
  1. Simulate 1000 concurrent users over an extended period (e.g., 24 hours).
  2. Check for memory leaks, system slowdowns, and transaction failures.
  3. **Expected Result:** The system should remain stable, with no memory leaks or degradation in performance.

---

### **6. Defect Reporting and Management**

During test execution, any issues or defects encountered should be logged in a defect tracking system, such as Jira or Bugzilla, with detailed steps for reproduction, severity, and screenshots/logs where necessary.

---

### **7. Test Summary Report**

After all tests are executed, a **Test Summary Report** will be generated, covering:
- Test case execution status (pass/fail).
- Identified defects with severity.
- Performance test results (response time, throughput, error rates).
- Recommendations for improvement (if any).

---

### **8. Conclusion**

The successful execution of these test cases will validate that the multi-currency payment system can accurately process transactions in multiple currencies, handle errors gracefully, and provide consistent user experience across all supported currencies.

---

**End of Document**

# Load Test for BlazeDemo 🚀

[](https://github.com/0xmuchen/performance-testing-blaze-demo#load-test-for-blazedemo-)

This repository contains performance testing scripts for the BlazeDemo website using both **Apache JMeter** and **k6**. The tests simulate load and performance metrics by sending HTTP requests to the application and checking response times ⏱️ and correctness ✅.

## Test Plan Overview 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#test-plan-overview-)

The test plan consists of the following main parts:

1. **JMeter Tests**: Simulates 10/100/1000 users performing various operations such as searching for tickets ✈️, selecting a flight, and confirming a booking.
2. **k6 Tests**: Another method to simulate load, perform the same operations, and generate performance reports.
3. **Assertions**: Response code and content assertions to verify the correctness of the server's response.
4. **Results Collection**: Collects detailed test results, including response times, latency, and success status for both JMeter and k6.

## Requirements 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#requirements-%EF%B8%8F)

- [Apache JMeter](https://jmeter.apache.org/) 5.6.3 or later
- [k6](https://k6.io/docs/) 0.44.0 or later
- Java 8 or later ☕️

## How to Run 🏃‍♂️

[](https://github.com/0xmuchen/performance-testing-blaze-demo#how-to-run-%EF%B8%8F)

### Running JMeter Test

[](https://github.com/0xmuchen/performance-testing-blaze-demo#running-jmeter-test)

1. Download and install [Apache JMeter](https://jmeter.apache.org/).
    
2. Clone this repository to your local machine 💻.
    
3. Open JMeter `bin` folder in the terminal.
    
4. To run the JMeter test from the command line, use the following command:
    
    ```shell
    ./jmeter -n -t ${PATH_TO_TEST_PLAN}/LoadTestBlazeDemo.jmx -JUSERS_COUNT=${THREADS_NUMBER} -l <path_to_results_folder>/Results-${THREADS_NUMBER}-users.jtl -e -o ${PATH_TO_RESULTS_FOLDER}/Test-Report-${THREADS_NUMBER}
    
    ```
    

### Running k6 Test

[](https://github.com/0xmuchen/performance-testing-blaze-demo#running-k6-test)

1. Install [k6](https://k6.io/docs/getting-started/installation/) if you haven't already.
    
2. Clone this repository to your local machine 💻.
    
3. Navigate to the `k6` folder containing the test scripts.
    
4. Run the k6 test with the following command:
    
    ```shell
    k6 run loadtest.js --vus ${THREADS_NUMBER} --duration 30s
    
    ```
    

## GMeter Test Plan Structure 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#gmeter-test-plan-structure-)

The test plan includes the following:

- **Thread Group**: Configures the number of threads (users) and ramp-up time ⏳.
- **HTTP Request Samplers**: Sends HTTP requests to the BlazeDemo website (searching, selecting flights, and booking tickets) ✈️.
- **Assertions**: Ensures that the response codes and content are correct.
- **Result Collectors**: Saves test results for further analysis.

## GMeter Example Report 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#gmeter-example-report-)

[![Response Time Screenshot](https://github.com/0xmuchen/performance-testing-blaze-demo/raw/master/demo/ResponseTime.png)](https://github.com/0xmuchen/performance-testing-blaze-demo/blob/master/demo/ResponseTime.png)

## K6 Example Report 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#k6-example-report-)

[![K6 Logs Screenshot](https://github.com/0xmuchen/performance-testing-blaze-demo/raw/master/demo/K6Logs.png)](https://github.com/0xmuchen/performance-testing-blaze-demo/blob/master/demo/K6Logs.png)

## Link to BlazeDemo 

[](https://github.com/0xmuchen/performance-testing-blaze-demo#link-to-blazedemo-)

Visit the BlazeDemo website for more details: [https://blazedemo.com/](https://blazedemo.com/)

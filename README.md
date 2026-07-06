# FlexilantSql
1.  Why did you use INNER JOIN, LEFT JOIN, NOT EXISTS, or another approach?
Used different type of joins to indicate how the data should be pulled and from which table

2. What would change if product_id was not unique?
Will use distinct function to bring out the uniquer values

3. What issue could happen if price or status can be NULL?
Join condition will fail 

---------------------------------------------------------

# API Test Cases



# Test Case 1
# Test Name: Retrieve Valid Order Successfully

Input:
GET /api/orders/ORD-1001

Expected Result:
- HTTP Status Code: 200 OK
- Response contains:
  - order_id = "ORD-1001"
  - customer_id
  - amount
  - currency
  - status
  - created_at
- All values match the expected order details.

Why this test is useful:
This verifies that the API successfully returns the correct order details for a valid order ID.

--------------------------------------------------

# Test Case 2
# Test Name: Order Not Found

Input:
GET /api/orders/ORD-9999

Expected Result:
- HTTP Status Code: 404 Not Found
- Error message such as "Order not found".

Why this test is useful:
This ensures the API correctly handles requests for orders that do not exist.

--------------------------------------------------

# Test Case 3
# Test Name: Invalid Order ID Format

Input:
GET /api/orders/INVALID@123

Expected Result:
- HTTP Status Code: 400 Bad Request
- Error message indicating an invalid order ID format.

Why this test is useful:
This verifies that the API validates user input and rejects invalid order IDs.

--------------------------------------------------

# Test Case 4
# Test Name: Missing Order ID

Input:
GET /api/orders/

Expected Result:
- HTTP Status Code: 404 Not Found or 405 Method Not Allowed
- Appropriate error message.

Why this test is useful:
This confirms that the API handles incomplete requests correctly without returning invalid data.

--------------------------------------------------

# Test Case 5
# Test Name: Validate Response Data Types

Input:
GET /api/orders/ORD-1001

Expected Result:
- HTTP Status Code: 200 OK
- order_id and customer_id are strings.
- amount is a numeric value.
- currency is "GBP".
- status contains a valid value (e.g., PAID).
- created_at is in valid ISO 8601 date-time format.

Why this test is useful:
This ensures the API response follows the expected schema and data types, helping prevent application errors.
-----------------------------------


# API Task 2 – Simple Automated Test (Postman Pseudo Code)

pm.test("Verify order returns HTTP 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Verify order status is PAID", function () {
    var response = pm.response.json();
    pm.expect(response.status).to.eql("PAID");
});

The response status code is 200.
The status field in the response body is "PAID".

-----------------------------------------------
# README

## 1. Language Used

* Java for the CSV comparison tool.
* SQL for the database queries.
* Postman-style JavaScript for the API test example.

## 2. How to Run the CSV Comparison Tool

1. Install Java

2. Place the input CSV files in the project folder.

3. Open a terminal or command prompt.

4. Click on Run

5. The tool will compare the CSV files and display or save the comparison results.

## 3. How to Run the Tests

* Open Postman.
* Import the API collection (if provided).
* Send the request:
  GET /api/orders/ORD-1001
* Verify that:

  * HTTP Status Code is 200.
  * The response field "status" is "PAID".
* Alternatively, run the collection using the Postman Collection Runner.

## 4. SQL Answers

The SQL queries required for the assessment are included in the SQL solution file and were written using standard SQL syntax.

## 5. API Test Cases

The following API test cases were designed:

1. Retrieve a valid order successfully.
2. Request a non-existent order.
3. Request using an invalid order ID format.
4. Request with a missing order ID.
5. Validate response schema and data types.

## 6. Assumptions Made

* The API follows REST standards.
* A valid order ID returns HTTP 200.
* A non-existent order returns HTTP 404.
* Invalid input returns HTTP 400.
* The response format matches the sample JSON provided.
* The order status "PAID" is a valid status value.

## 7. AI Usage Statement

AI was used to assist with improving the wording, formatting, and presentation of the solutions. All answers were reviewed and verified before submission.

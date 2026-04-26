# Qa-Project-4-API-Testing
<p align="left">
  <img src="assets/images/API.png" alt="web application Welcome Screenshot" width="800">
</p>

## 📋 Project Description
API testing on Urban.Grocers backend services, validating REST endpoints, HTTP responses, and business rules using Postman.

---

### 📂 Project Resources & Assets
* **📋 Requirements:** [View Functional Requirements (PDF)](https://practicum-content.s3.us-west-1.amazonaws.com/new-markets/qa-sprint-3/QA_3.1.1_Requisitos_para_el_back-end_de_Urban.grocers.pdf)

<details>
    <summary><b><i>Click here to view 🚀 API Documentation</i></b></summary><br>

   **🚀 API Documentation (Endpoints):**
   The project interacts with REST (JSON) and SOAP services. Below is an example of the **warehouse and service validation:**

| Endpoint | Method | Format | Auth | Description |
| :--- | :--- | :--- | :--- | :--- |
| `/big-world/wsdl` | POST | SOAP (XML) | NONE | Stock check for the "Big World" warehouse. |
| `/api/v1/users` | POST | JSON | NONE | User account creation. |
| `/api/v1/kits` | POST | JSON | Bearer Token | Custom kit creation and product grouping validation. |
| `/api/v1/kits/:id/products` | POST | JSON | NONE | **Main.Kits:** Add products to kit. | 
| `/api/v1/kits/:id` | DELETE | JSON | NONE | **Main.Kits:** Delete kit. | 
| `/api/v1/products/kits` | GET | JSON | NONE | **Main.Products:** Search for kit by product. | 
| `/api/v1/kits` | GET | JSON | NONE | **Main.Kits:** Get all kits. Retrieves the complete list of available kits. |
| `/api/v1/kits?cardId={id}` | GET | JSON | NONE | **Main.Kits:** Get kit by Card ID. Filters and retrieves a specific kit. |
| `/order-and-go/v1/delivery` | POST | JSON | NONE | **Couriers:** "Order and Go" delivery validation. |

> **Note:** The full documentation is integrated within the project container. I have included an export of the Postman collection with request examples in the `/docs` folder.
</details>

---

## ✅ Activities Performed

🔍 **Requirement Analysis:** Thorough review of the **Urban.Grocers** back-end documentation **(Apidoc)** to identify business rules and technical constraints.

📝 **Test Design & Strategy:** Developed comprehensive **Checklists** and test cases using Google Sheets, applying **Black Box techniques** to ensure full functional coverage.

🚀 **Postman Collection Engineering:** Structured and configured API request collections, including environment variables and dynamic parameters for efficient testing.

🧪 **API Testing Execution:** Conducted manual and functional testing of **REST and SOAP** endpoints to validate data integrity and system response.

🐛 **Defect Management:** Identified, documented, and reported critical integration bugs using **Jira**, ensuring clear reproduction steps for the development team.

📊 **Results Documentation:** Organized all testing artifacts and outcomes to provide a transparent overview of the system's stability before production.

## 📑 Test Planning & Strategy

<table width="100%">
<tr>
<td width="30%"><b>🎯 Scope</b></td>
<td>Functional testing of the <b>Urban.Grocers API</b>, focusing on Warehouse (SOAP), Kits, Products, and Courier (REST) modules.</td>
</tr>
<tr>
<td><b>🚫 Out of Scope</b></td>
<td>Frontend/UI testing, automated test scripts (scripts/code), and performance/load testing.</td>
</tr>
<tr>
<td><b>✅ Entry Criteria</b></td>
<td>Access to the <b>Apidoc</b> documentation, active server environment (TripleTen container), and functional requirements finalized.</td>
</tr>
<tr>
<td><b>🏁 Exit Criteria</b></td>
<td>100% of designed checklists executed, all identified bugs reported in <b>Jira</b>, and final status report completed.</td>
</tr>
</table>

## 📊 Test Execution Metrics

<details>
  <summary><b><i>Click here to view Design Checklist Functional Validation: Main.Kits - Add Products to Kit details</i></b></summary>

  ##
   > **Project Overview:** Validation of the `/api/v1/kits/:id/products` endpoint.

#### 📝 Design Checklist

 | Category | Results |
  | :--- | :---: |
  | 🚀 **Total Tests Executed** | `52` |
  | ✅ Passed Cases | `33` |
  | 🐞 Failed Cases (Bugs Found) | `19` |
  | 🚨 Critical/High Severity Defects| `6` |

## 📂 Project Documentation
[Functional Validation: Main.Kits_Add Products to Kit-Checklist](https://docs.google.com/spreadsheets/d/1wQ4V7dnGUI24XoK_e8gDvZ0PdoJxq9p6GwnVnX_lvcY/edit?usp=sharing)

<div align="center">
  <video src="https://github.com/user-attachments/assets/88b8e2a2-3bdd-4f9f-9ef7-085b5040cc9e" width="90%"></video>
  <p><b><i>🐛 Bug Alert:The `Main.Kits` endpoint fails to enforce the logical constraint, incorrectly accepting requests that include more than 30 products in a single kit.</i></b></p>
</div>

</details>

<details>
  <summary><b><i>Click here to view Delivery Service details</i></b></summary>

 #### 🚚 Delivery Service - Test Execution Summary
 > **Project Overview:** Validation of the `/order-and-go/v1/delivery` endpoint using Boundary Value Analysis and Equivalence Partitioning.
 
| Category | Results |
  | :--- | :---: |
  | 🚀 **Total Tests Executed** | `57` |
  | ✅ Passed Cases | `42` |
  | 🐞 Failed Cases (Bugs Found) | `15` |
  | 🚨 Critical/High Severity Defects| `13` |

## 📂 Project Documentation

[Delivery Service -Checklist](https://docs.google.com/spreadsheets/d/19wM9g8drlzGF2JIr4nNHSdY3BCet-pzQwzVBMoZ9ngs/edit?usp=sharing)


<div align="center">
  <video src="https://github.com/user-attachments/assets/4a737380-cc29-4bc2-8ae3-5c5b05baefa2" width="90%"></video>
  <p><b><i>🎥 Logic Error: Invalid Delivery Times returning 200 OK .</i></b></p>
</div>

 
</div>
</details>




<details>
  <summary><b><i>🐞 Click here to view Bug Report: Critical Logic Error in Delivery Costs details</i></b></summary>

  ## 🐛 [ID: PROYEC-32] – Critical Input Validation Failure & Cost Calculation Error

* **Severity:** 🛑 **Critical** (Direct impact on profitability and business logic failure).
* **Priority:** **High** ⬆️
* **Component:** `Order and Go` Service API.

### 📝 Description
The endpoint `/order-and-go/v1/delivery` fails to sanitize and validate input parameters. It accepts invalid negative values and returns a `200 OK` status, leading to incorrect **delivery cost calculations** and a direct violation of established business rules.

### 🎬 Evidence & Technical Analysis
The following video demonstrates how the system processes a payload that violates two core constraints: **Negative product quantity** and **Weight threshold inconsistency**.

<div align="center">
  <video src="https://github.com/user-attachments/assets/5d4f0b95-7ea6-435f-8eb3-65e2ed83fac7" width="75%"></video>
  <p><b>🎥 Execution: Negative Value Testing & Cost Validation</b></p>
</div>

> **Key takeaway from video:** Note that when sending `"productsCount": -1`, the system ignores the invalid integer, responds with `200 OK`, and sets `clientDeliveryCost` to `0`, bypassing the required minimum cost.

---

### 🛠️ Bug Details (Expected vs. Actual)

| Field | Input Data (Payload) | Expected Result | Actual Result |
| :--- | :--- | :--- | :--- |
| **Products Count** | `-1` | `400 Bad Request` | `200 OK` (Accepted) |
| **Delivery Cost** | Weight: `3 kg` | `ClientDeliveryCost: 3` | `ClientDeliveryCost: 0` |

**Steps to Reproduce:**
1. Send a `POST` request to `/order-and-go/v1/delivery`.
2. Use the following payload:
   ```json
   {
     "deliveryTime": 8,
     "productsCount": -1,
     "productsWeight": 3
   }

3. Check the HTTP response code and the cost fields in the JSON body.

**Defect Impact:**
* **Financial:** Direct revenue loss per order due to underestimated service costs ($0 instead of $3) and acceptance of negative counts.
* **Data Integrity:** Risk of database corruption by allowing records with impossible product quantities (negative values).


### 💻 Testing Environment.
* **Tools:** Postman.
* **OS:** Linux Mint.

 
</div>
</details>


---

### ⚠️ Issues Identified

<div style="background-color: #fff5f5; border-left: 5px solid #ff4444; padding: 15px; color: #333;">
  <ul>
    <li>Critical Validation Gap.</li>
    <li>Business Logic Inconsistency.</li>
    <li>Boundary Value Vulnerabilities.</li>
    <li>Data Integrity Risk.</li>
    <li>False Positive Responses.</li>
  </ul>
  <hr>
  </p>
</div>


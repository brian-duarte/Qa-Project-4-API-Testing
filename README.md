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
  <summary><b><i>Click here to view 🐞 Featured Bug Report - Product Count, Weight, & DeliveryCost details</i></b></summary>

##

🐛 **[ID:PROYEC-22 / PROYEC-23 / PROYEC-35]** – **Error en validación de productsCount & productsWeight**
* **Severidad:** 🛑 Crítica (Afecta el cálculo de costos y la lógica de negocio).
* **Priority:** High ⬆️
* **Descripción:** El sistema procesa valores de entrada inválidos (ej. cantidades negativas o tipos de datos no numéricos) sin detener la solicitud, retornando un 200 OK.

* **Pasos para reproducir:**

Enviar una petición POST a /order-and-go/v1/delivery.

Incluir:
"deliveryTime": 8,
    "productsCount": -1,
    "productsWeight": 3

* **Resultado esperado:** El servidor debe rechazar la solicitud con un código 400 Bad Request.

* **Resultado actual:** El sistema responde 200 OK y calcula costos erróneos.
  
    "name": "Order and Go",
  
    "isItPossibleToDeliver": true,
  
    "hostDeliveryCost": 3,
  
    "toBeDeliveredTime": {
  
        "min": 20,
  
        "max": 25
  
    },
  
    "clientDeliveryCost": 0
  

* Evidence:




* Environment:

 
</div>
</details>










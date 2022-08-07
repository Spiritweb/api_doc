**TLC Broker API Documentation**
----

* **URL / API Endpoint**

  `https://dev.tlc.com.au/api/v1/application/submit`

* **Method:**

  `POST`
  
*  **Authentication**
    
    API Token should be pass on Header
    as `Bearer` Token

*  **Conten Type**
    
    Content Type must be JSON on Header
    as 
    ```
    Accept: 'application/json'
    Content-Type: 'application/json'
    ```

* **Data Params**

  ```json
    {
        "customer": {
          "first_name": "Matthew",
          "middle_name": "Love",
          "last_name": "Hunt",
          "email": "mahfuz@testtlc.com",
          "mobile": "0467676756",
          "gender": "Male",
          "date_of_birth": "1970-01-26"
        },
        "address": {
          "unit_no": "12",
          "street_no": "4",
          "street_name": "Huntsman",
          "street_type": "CTR",
          "city": "Pyromont",
          "state": "NSW",
          "postcode": "2011",
          "is_current": true,
          "years_at_address": "30",
          "months_at_address": "12"
        }
        "identity": {
          "driving_licence": "DRV2345235",
          "driving_licence_expiry": "2022-12-31",
          "driving_licence_state": "NSW"
        },
        "purpose": "Vehicle",
        "amount": 15000,
        "loan_term": 60,
        "marital_status": "Married",
        "dependents": "0",
        "annual_income": "111111",
        "employment_status": "Full-Time",
        "living_status": "Living with Parents",
        "agreement": {
          "privacy_disclosure": true,
          "credit_guide_quote: true,
          "electronic_communication" true,
          "credit_report": true
        }
    }
  ```
  
  ### Important Note
  > * `title` must be an item from [Title Field](#title)
  >
  > * `purpose` must be an item from [Loan Purposes](#loan-purpose)
  > 
  > * `empl_status` must be an item from [Employment Status](#employment-status)
  >
  > * `living_status` must be an item from [Living Status](#living-status)
  >
  > * `marital_status` must be an item from [Marital Status](#marital-status)
  >
  > * `amount` must be between `2000` to `50000` & `integer` type all other fields are `string`
  > 
  > And these fields are case-sensitive `Dental` & `dental` is not same.
  >
  > All the fields are required except `current_unit_no`

  
  # Title
    * `Mr`
    * `Mrs`
    * `Miss`
    * `Ms`
  
  # Loan Purpose
    * `Bariatric Surgery`
    * `Cosmetic Dental`
    * `Cosmetic Surgery`
    * `Debt Consolidation`
    * `Dental`
    * `Dental Fees`
    * `Dental Implant`
    * `ENT Surgery`
    * `Education`
    * `Endodontic Fees`
    * `Engagement Ring`
    * `Eye Surgery`
    * `Garages`
    * `General Wedding Cost`
    * `Holiday`
    * `Home Improvements`
    * `Honeymoon`
    * `IVF Programs`
    * `Jewellery`
    * `Kit Homes`
    * `Lifestyle`
    * `Medical`
    * `Oral and Maxillofacial Fees`
    * `Orthodontic`
    * `Periodontics Fees`
    * `Plastic Surgery`
    * `Pool or Spa`
    * `Renovations`
    * `Solar Systems`
    * `Sports Equipment`,
    * `Sports Activity`,
    * `Vascular Surgery`
    * `Vehicle`
    * `Watch`
    * `Wedding`
   
  # Employment Status
    * `Full-Time`
    * `Part-Time`
    * `Self-Employed`
    * `Casual`
    * `Centrelink`

  # Living Status
    * `Owner`
    * `Mortgage`
    * `Renting`
    * `Living with Parents`
    * `Boarding`
    
  # Marital Status
    * `Single`
    * `Defacto`
    * `Married`
    * `Divorced`
    * `Widowed`

---

* **Success Response:**
  * **Code:** 201 <br />
    **Content:** `{ "success": "Application Submitted" }`
 
* **Error Response:**
  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ "message": "Unauthenticated." }`

  OR

  * **Code:** 422 UNPROCESSABLE ENTRY <br />
    **Content:** 
    ```{
       "message": "The given data was invalid.",
       "errors": {
         "living_status": [
           "The living status field is required."
         ]
       }
     }
  
  OR

  * **Code:** 405 UNPROCESSABLE ENTRY <br />
    **Content:** `{ "message": "The POST method is not supported for this route. Supported methods: GET, HEAD."}`

* **Notes:**

    * Contact: `william@tlc.com.au`

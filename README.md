**TLC Broker API Documentation**
----

* **URL**

  `https://admin.tlc.com.au/api/create_app`

* **Method:**

  `POST`
  
*  **Authentication**
    
    API Token should be pass on Header
    as `Bearer` Token


* **Data Params**

  ```json
    {
        "purpose": "Vehicle",
        "amount": 15000,
        "email": "mahfuz@testtlc.com",
        "mobile": "0467676756",
        "title": "Mr",
        "first_name": "Matthew",
        "last_name": "Hunt",
        "gender": "Male",
        "date_of_birth": "11-11-2003",
        "marital_status": "Married",
        "dependents": "0",
        "current_unit_no": "12",
        "current_street_no": "4",
        "current_street_name": "Huntsman",
        "current_street_type": "CTR",
        "current_city": "Pyromont",
        "current_state": "NSW",
        "current_postcode": "2011",
        "time_at_current_year": "30",
        "time_at_current_months": "12",
        "yearly_income": "111111",
        "employment_status": "Full-Time",
        "living_status": "Living with Parents"
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

    * Contact: `admin@tlc.com.au`

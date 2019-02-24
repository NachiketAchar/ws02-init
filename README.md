# ws02-init
Downloaded the WS02 EI, create a sample proxy and save it to GITHub: 
Downloaded API Manager and Enterprise Integrator and configured them to communicate. 
Created an API using Enterprise Integrator. 
Created a test that connects to the API you have created, through API Manager, and returns a response.

This proxy is dependant on the the MSF4J service available here - https://github.com/wso2-docs/WSO2_EI/blob/master/Back-End-Service/Hospital-Service-2.0.0.jar

This proxy does -
- gives a list of available doctors for a certain category.
- for a category reserves an appointment with a doctor.
- It has a transformation of json payload from a flat structure to a nested structure using the datamapper option.
- This proxy has the following endpoints 
  - GET on http://[host]:[port]/healthcare/querydoctor/{category}
      - category can be surgery, cardiology, gynaecology, ent, paediatric

  - POST on http://[host]:[port]/healthcare/categories/surgery/reserve
      - json body as below 
        {
          "name": "John Doe",
          "dob": "1940-03-19",
          "ssn": "234-23-525",
          "address": "California",
          "phone": "8770586755",
          "email": "johndoe@gmail.com",
          "doctor": "thomas collins",
          "hospital": "grand oak community hospital",
          "cardNo": "7844481124110331",
          "appointment_date": "2017-04-02"
        }
      - The proxy routes to different endpoints based on the hospital key value in the json object body
     

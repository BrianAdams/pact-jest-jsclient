Description
-----------
This is a POC for using PACT.io using jest as the testing infrastructure.  This project is the example of a client application that would consume the API.  Using customer contrats, this means this project stands up the mock API that returns data and then hands the resulting contract specification off to the provider project to validate against when the actual provider service is being written.

To install
`npm install`

To run the test and generate the contract:
`npm test`

The resulting contract will be found in `pacts\myconsumer-muprovider.json`

The generated contract look like:

```json
{
  "consumer": {
    "name": "MyConsumer"
  },
  "provider": {
    "name": "MyProvider"
  },
  "interactions": [
    {
      "description": "a request for projects",
      "providerState": "i have a list of projects",
      "request": {
        "method": "GET",
        "path": "/dogs",
        "headers": {
          "Accept": "application/json"
        }
      },
      "response": {
        "status": 200,
        "headers": {
          "Content-Type": "application/json"
        },
        "body": [
          {
            "dog": 1
          }
        ]
      }
    }
  ],
  "metadata": {
    "pactSpecification": {
      "version": "2.0.0"
    }
  }
}
```
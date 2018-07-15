coffeeshops
A JSON RESTful service in node.js to maintain a list of coffee shops and to find the nearest one to an input address.

It consists of three files:
app.js - starts the service and handles the endpoints
coffee_shops.js - manages the coffee shop info repository
locations.csv - the coffee shop info loaded on startup

Dependencies:
npm install express
npm install joi
npm install @google/maps
(If you are using an older version of npm, add the --save option.)

The service listens on port 3000 by default, or on the port specified in the PORT environment variable.

JSON Endpoints:

LOOKUP: Request: POST /api/coffeeshop/lookup { id: integer } response: { id: integer, name: string, address: string, lat: real, lon: real }

CREATE: Request: POST /api/coffeeshop/create { id: integer, name: string, address: string, lat: real, lon: real } Response: { id: integer }

UPDATE: Request: PUT /api/coffeeshop/update { id: integer, name: string, address: string, lat: real, lon: real } Response: { id: integer }

DELETE: Request: DELETE /api/coffeeshop/delete { id: integer } Response: { id: integer }

FIND NEAREST: Request: POST /api/coffeeshop/nearest { address: string } Response: { name: string }

ERRORS - When errors are encountered, such a an invalid ID or invalid LAT/LON, a 404 error is returned with an explanatory message.

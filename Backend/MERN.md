# MERN STACK
### HTTP Request

GET - request resource
POST - sending resource to server (form submit)
PUT - replace a resource by changing it completely
PATCH - patch up a resource
DELETE - deleting resource

### HTTP Response status code

100 - 199 = Informational responses
200 -299 = Successful responses
300 - 399 = Redirection responses
400 - 499 = Client error messages
500 - 599 = Server error messages

### Middlewares

Different types of middle wares

1. Application level middlewares: These are defined in the app level and uses next()
2. Router level middlewares
3. Error Handling Middlewares
4. BUilt in Midddlewares: express.static, express.json, express.urlencoded when data is passed in body 
5. Third party Middlewares:

Examples of third party middlewares are:

1. Preprocessing - body-parser *, cors *, cookie-parser *, express-sessions *, multer *, connect-flash, compression

2. Authentication - passport *

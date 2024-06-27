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
3. Error handling- error handling middleware
4. Loggin req - morgan *
5. Security -  helmet *, express-rate-limit *

### Setting up live server

```js
import express from "express"
import 'dotenv/config'
const port = process.env.PORT || 3000
const app = express()
app.get("/",(req,res)=>{
    res.send("Hello World")
})

app.listen(port,()=>{
    console.log(`Listening on port ${port}`);
})
```
### Connecting MongoDB and setting server + cors error and .env
* DB
```js
import mongoose from "mongoose"
import { DB_NAME } from "../constants.js"

const connectDB = async()=>{
    try {
       const connection_instance = await mongoose.connect(`${process.env.URL}/${DB_NAME}`)
       console.log(`\n MongoDB Connected ${connection_instance.connection.host}`);
    } catch (error) {
        console.log("MongoDB connection failed", error);
        process.exit(1)
    }
}

export default connectDB
```
* main index.js
```js
import {app} from "./app.js"
import dotenv from "dotenv"
import cors from "cors"
import express from "express"
import connectDB from "./db/index.js"

const Port =process.env.PORT || 8000

app.use(
    cors({
        origin: process.env.CORS_ORIGIN,
        credentials: true
    })
)
//common middlewares
app.use(express.json({ limit: "16kb"}))
app.use(express.urlencoded({extended:true, limit: "16kb"}))
app.use(express.static("public"))
dotenv.config({
    path: "./.env"
})
connectDB()
.then(()=>{
    app.listen(Port, ()=>{
        console.log(`Server is running on Port ${Port}`);
    })
})
.catch((err=>{
    console.log("MongoDB Connection error", err);
})
)
```

# **API Specifications**

## **Users**

### **A. Register**

- Method : POST
- Endpoint : user/register
- Body :

```
{
    name:  String,
    email: {
        type: String,
        required: true
    },
    password: String
}
```

- response

```
{
        "message": "Succes Register!"
}
```

### **B. Login**

- Method: POST
- Endpoint: /login
- Body:

```
{
    "email":"string",
    "password": "string"
}
```

- Response:

```
{
          "message": "Login Succesfull!",
          "token",
}
```

## **ToDo**

### **A. Get All Todo**

- method : GET
- Endpoint: /todo
- HTTP Header :
  - auth-token : `token`
- Response :

```
{
  "message": "Getting Data",
  "data": [
    {
      "_id": "ObjectId",
      "name": "string",
      "user": {
        "_id": "ObjectId",
        "name": "string"
      }
    }
]
}
```

### **B. Get Todo By ID**

- method : GET
- Endpoint: todo/:id
- HTTP Header:
  - auth-token: `token`
- Response:

```
{
  "message": "You Searched for",
  "data": {
    "_id": "ObjectId",
    "name": "string",
    "user": "ObjectId"
  }
}
```

### **C. Update Todo By ID**

- Method : PATCH
- Endpoint: todo/:id
- HTTP Header:
  - auth-token: `token`

- Body : 
```
{
  "name" : "updated name"
}

```  
- Response :

```
    {
  "message": "Todo updated",
  "data": {
    "_id": "ObjectId",
    "name": "updated name",
    "user": "ObjectId"
  }
}
```

### **D. Delete Task By ID**

- Method : DELETE
- Endpoint: todo/:id
- HTTP Header:
  - auth-token: `token`
- Response :

```
{
  "message": "Data Deleted!"
}
```

### **E. Delete All Todos**

- Method : DELETE
- Endpoint: todo/
- HTTP Header:
  - auth-token : `token`
- Response :

```
{
    message: "All Data Deleted!",
}
```

### **F. Add Todo**

- Method : POST
- Endpoint : todo/add
- HTTP Header : 
  - auth-token : `token`
- Response : 

```
{
  "name" : "string",
  "user" : "user.ObjectId"
}
```
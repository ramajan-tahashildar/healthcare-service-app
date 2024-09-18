# Healthcare Services API

This is a simple API built using Node.js, Express, and MongoDB to manage a list of healthcare services. It allows users to add, update, retrieve, and delete healthcare services.

## Features

- **Add a new service**: Add a healthcare service with a name, description, and price.
- **Get all services**: Retrieve a list of all available services.
- **Update a service**: Modify the details of an existing service.
- **Delete a service**: Remove a service from the database.

## Technologies Used

- Node.js
- Express
- MongoDB (Mongoose)
- Postman (for testing)

## Requirements

- Node.js
- MongoDB

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/healthcare-services-api.git
```

2. Navigate to the project directory:

```bash
cd healthcare-services-api
```

3. Install the dependencies:

```bash
npm install
```

4. Create a `.env` file in the root of your project and add your MongoDB connection string:

```bash
MONGODB_URI=your-mongodb-connection-string
```

5. Start the server:

```bash
npm start
```

The API will be running on `http://localhost:3000`.

## API Endpoints

### Add a New Service

- **Endpoint**: `POST /services`
- **Description**: Add a new healthcare service.
- **Request Body**:

```json
{
  "name": "Service Name",
  "description": "Service Description",
  "price": 100
}
```

- **Response**:

```json
{
  "_id": "serviceId",
  "name": "Service Name",
  "description": "Service Description",
  "price": 100
}
```

### Get All Services

- **Endpoint**: `GET /services`
- **Description**: Retrieve a list of all available healthcare services.
- **Response**:

```json
[
  {
    "_id": "serviceId",
    "name": "Service Name",
    "description": "Service Description",
    "price": 100
  },
  {
    "_id": "serviceId2",
    "name": "Service Name 2",
    "description": "Service Description 2",
    "price": 200
  }
]
```

### Update a Service

- **Endpoint**: `PUT /services/:id`
- **Description**: Update the details of an existing healthcare service.
- **Request Body**:

```json
{
  "name": "Updated Service Name",
  "description": "Updated Service Description",
  "price": 150
}
```

- **Response**:

```json
{
  "_id": "serviceId",
  "name": "Updated Service Name",
  "description": "Updated Service Description",
  "price": 150
}
```

### Delete a Service

- **Endpoint**: `DELETE /services/:id`
- **Description**: Remove a service from the list.
- **Response**:

```json
{
  "message": "Service deleted successfully"
}
```

## Database Schema

The healthcare service schema includes the following fields:

- **name**: String (required)
- **description**: String
- **price**: Number (required)

## Basic Validation

- **Service Name**: Required
- **Price**: Required, must be a number.

## How to Run Tests

You can use [Postman](https://www.postman.com/) or any other API testing tool to test the endpoints.

1. Import the API collection in Postman.
2. Send requests to the API and verify the responses.

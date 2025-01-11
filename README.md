# FastAPI Test Application

This is a simple FastAPI application that demonstrates the use of basic endpoints for handling HTTP requests.

## Features

- **Root Endpoint**: Responds with a simple greeting message.
- **Addition Endpoint**: Takes two integers as input and returns their sum.
- Automatically generated API documentation using OpenAPI and Swagger UI.
- **Swagger UI and ReDoc**: Interactive API documentation available at `/docs` and `/redoc`.

## Endpoints

### 1. Root Endpoint

**GET /**

- **Description**: Returns a greeting message.
- **Response**:
  ```json
  {
      "message": "Hello World!"
  }
  ```

### 2. Addition Endpoint

**GET /add/{num1}/{num2}**

- **Description**: Adds two numbers together.
- **Parameters**:
  - `num1` (int): The first number.
  - `num2` (int): The second number.
- **Response**:
  ```json
  {
      "total": <sum_of_num1_and_num2>
  }
  ```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/hwang2006/fastapi-test
   cd fastapi-test
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the dependencies:
   ```bash
   pip install fastapi uvicorn
   ```

## Running the Application

Start the application using the following command:
```bash
python main.py
```
or

```bash
uvicorn main:app --host 0.0.0.0 --port 8080 --reload
```



Replace `main` with the name of the Python file if it is different.

- The app will be accessible at: `http://127.0.0.1:8080`
- Open the automatically generated API documentation:
  - Swagger UI: [http://127.0.0.1:8080/docs](http://127.0.0.1:8080/docs)
  - ReDoc: [http://127.0.0.1:8080/redoc](http://127.0.0.1:8080/redoc)

## Testing

You can test the endpoints manually using:
- **Swagger UI**: Open [http://127.0.0.1:8080/docs](http://127.0.0.1:8080/docs) in your browser and test each endpoint interactively.
- **ReDoc**: Open [http://127.0.0.1:8080/redoc](http://127.0.0.1:8080/redoc) for an alternative documentation style.
- **cURL**:
  ```bash
  # Test root endpoint
  curl http://127.0.0.1:8080/

  # Test addition endpoint
  curl http://127.0.0.1:8080/add/5/10
  ```

## Example

### Request:
```bash
GET /add/4/7 HTTP/1.1
Host: 127.0.0.1:8080
```

### Response:
```json
{
    "total": 11
}
```


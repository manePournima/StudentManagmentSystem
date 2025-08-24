#  Student Record Management
Designed and implemented a secure Spring Boot REST API for Student Record Management, featuring JWT-based authentication. Provides full CRUD operations with robust input validation, automatic calculation of student percentage, and division classification. All /api/students/** endpoints are secured and ready for Postman testing.

**Getting Started**
Prerequisites

    -Java 17+
    -Maven
    -Postman (for testing APIs)

**Git (for cloning repo)**
  
    git clone https://github.com/manePournima/Student-Record-Management.git
    cd Student-Record-Management
    mvn clean install
    mvn spring-boot:run

**API Endpoints**

1. Authenticate User (Login)

       POST: /api/auth/login
   
        Payload:
            {
              "username": "admin",
              "password": "password"
            }
   
        Response:
           {
               "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhZG1pbiIsImlhdCI6MTc1NjAx...."
           }


**Note: Copy this token. You will need it to access all /api/students/endpoints.**


**2. Create Student**

    POST: /api/students

    Headers:

    Authorization: Bearer <copied_token>

    Payload:

      {
      "name": "John Doe",
      "age": 20,
      "marks1": 80,
      "marks2": 75,
      "marks3": 90,
        "marks4": 85,
        "marks5": 70
    }


**Response: Student object with calculated percentage and division.**


**3. Get All Students**


      GET: /api/students

    Authorization: Bearer <copied_token>

Response: List of student objects with details, percentage, and division.

**4. Update Student**

    PUT: /api/students/{id}


    Authorization: Bearer <copied_token>

    Payload:

    {
    "name": "John Smith",
    "age": 21,
    "marks1": 85,
    "marks2": 80,
    "marks3": 90,
    "marks4": 75,
    "marks5": 80
    }


Response: Updated student object.

**5. Delete Student**

    DELETE: /api/students/{id}

    Authorization: Bearer <copied_token>

(Refer above endpoints section for examples)

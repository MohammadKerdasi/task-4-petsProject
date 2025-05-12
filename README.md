
#  Pet Adoption

## Project Structure

```
pet-adoption-platform/
├── controllers/
│   ├── petsController.js
│   ├── clinicsController.js
│   ├── articleConroller.js
├── routes/
│   ├── petsRoutes.js
│   ├── clinicsRoutes.js
│   ├── articleRoute.js
├── models/
│   ├── pet.js
│   ├── clinic.js
│   ├── article.js
├── middlewares/
│   └── errorHandler.js
├── app.js
└── README.md
│
│__ .env
│__ .gitignore


```
## Required Libraries

| Library          
|------------------
| `express`        
| `dotenv`         
| `morgan`         

---

## API Endpoints

### 1. Get Available Pets in a City

- **Endpoint:** `GET /api/pets`
- **Query Params:** `city` (string), `type` (optional: cat/dog)
- **Response:**
  ```json
  {
    "pets": [
      { "id": 1,
        "name": "Luna",
        "type": "dog",
        "city": "lattakia" 
      }
    ]
  }
  ```
- **Common Errors:**
  - Missing or invalid `city` query
  - Empty result (no pets found)

---

### 2. Find Open Emergency Clinics

- **Endpoint:** `GET /api/clinics/emergency`
- **Query Params:** `location`, `openNow=true`
- **Response:**
  ```json
  {
    "clinics": [
      { 
        "name": "mosto clinic",
        "distance": 2.5
      }
    ]
  }
  ```
- **Common Errors:**
  - Invalid or missing location
  - No clinics currently open

---

### 3. Search Articles by Pet Type

- **Endpoint:** `GET /api/articles`
- **Query Params:** `type` (cat/dog/other)
- **Response:**
  ```json
  {
    "articles": [
      { 
        "title": "How to Groom a Cat",
        "url": "/articles/grooming-cat" 
      }
    ]
  }
  ```
- **Common Errors:**
  - invalid pet type
  - No articles available

---

## ⚠️ Error Handling

- Return error messages and status code:
  ```json
  {
    "error": "Invalid city name",
    "code": 400
  }
  ```
---


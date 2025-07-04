# 🐾 Pet Center

Pet Center is a web application for managing pets in shelters. It supports user authentication, pet adoption workflows, automatic parsing of animals from ss.lv, and media storage. <br>
In the **backend** part, built using **ASP.NET Core**, **Entity Framework Core**, and **MongoDB**. <br>
In the **fontend** part, built using **React**, **HTML5, CSS**, **JavaScrypt**.

---

## ⚙️ Features

- 🔐 JWT authentication and user registration/login
- 🐶 Full accounting for pets, shelters, reviews and adoption requests
- 🔎 Auto-parsing pets from [ss.lv](https://www.ss.lv) with image importing
- 🧠 Breed, gender, age, and price resolvers using NLP and regex
- 🗄️ PostgreSQL (relational) + MongoDB (image storage)
- 🧾 Swagger UI for API testing and documentation
- 🔒 AES encryption of user data (email, phone, password)
- 🔁 Background service for automatic import

---

## 📁 .env Settings

At the root of the `backend/` folder, create a `.env` file:

```env
DB_HOST=localhost
DB_NAME=pet_shelter
DB_USER=postgres
DB_PASSWORD=your_postgres_password

JWT_KEY=your_jwt_secret_key
JWT_ISSUER=PetShelter
JWT_AUDIENCE=PetShelterClient
JWT_EXPIRE_MINUTES=60

MONGO_URI=mongodb://localhost:27017

ENCRYPTION_KEY=your_key_in_32_symbols
```

> Replace `your_postgres_password`, `your_jwt_secret_key` and `your_key_in_32_symbols` with your real values.
> And if you want work with docker make `DB_HOST=postgres` and `MONGO_URI=mongodb://mongo:27017`.

🔑 JWT Key Generation

```bash
# Using OpenSSL
openssl rand -hex 16

# Or using Python
python -c "import secrets; print(secrets.token_hex(16))"
```

🔒 Encryption Key Generation

```bash
# Using OpenSSL
openssl rand -hex 32

# Or using Python
python -c "import secrets; import string; print(''.join(secrets.choice(string.ascii_letters + string.digits) for _ in range(32)))"
```

---

## 🚀 Project Launch

In the terminal inside the `/meta` folder, run:

```Makefile
make
```

This will build and run the application.

---

## 🔎 Swagger UI

To test endpoints in browser, open:

```Provider
http://localhost:5000/swagger
```

You can use `/register` and `/login` to get a JWT token, authorize requests and more.

---

## 🧩 Tech Stack

- ASP.NET Core
- PostgreSQL + Entity Framework Core
- MongoDB (GridFS for images)
- AngleSharp (HTML parsing from ss.lv)
- BCrypt (password hashing)
- AES Encryption (sensitive data)
- BackgroundService (auto-import)
- Swagger / OpenAPI

---

## 📊 Project Tasks and Kanban

Development tasks are tracked using GitHub Projects:

🔗 [View Project Board](https://github.com/orgs/victoria-pet-shelter/projects/3)

---

## 🔵Docker

```Docker
docker pull alaner/pet_shelter_backend:latest
docker-compose up -d
```

> Make sure the wait-for-it.sh file is present and uses LF (Unix-style) line endings.

---

## 🧠 Contributors

- Project by [Alan Arzumanjan](https://github.com/alanarzumanjan) and [Mark Korobkin](https://github.com/maemolol)

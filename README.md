# Homework 13: SQL Service Implementation with `AbstractEmployeesServiceSql`

## 🧩 Task Definition

HW#13 focuses on implementing the abstract SQL-based employee service.  
The main goals are:

-   Complete all methods of the `AbstractEmployeesServiceSql` class (currently throw `"Not Implemented"`).
-   Implement full CRUD logic using **Knex** and **SQLite**.
-   Ensure all service tests pass successfully.

### 🧪 Running Tests

```bash
npm run test-service sqlite
```

✅ All tests must pass.

---

## 📝 Description

This homework introduces a **database-powered employee service layer**.
You will implement all SQL operations inside the abstract base class `AbstractEmployeesServiceSql`, which acts as a foundation for future database services.

Using **Knex.js** as a query builder and **SQLite** as the database engine, the service supports full CRUD operations for managing employees with persistent storage.

---

## 🎯 Purpose

-   Learn how to extend abstract classes and implement all required methods.
-   Practice SQL query writing using **Knex**.
-   Understand how to integrate database operations into the service layer.
-   Ensure your service passes all automated unit tests for correctness.

---

## ✨ Features

-   🧱 Abstract class pattern with concrete SQLite implementation
-   💾 Persistent storage using **SQLite**
-   ⚙️ CRUD operations for employee management:

    -   Get all employees or filter by department
    -   Retrieve a specific employee by ID
    -   Add a new employee record
    -   Update employee details
    -   Delete employee by ID

-   🧩 Integration with service registry via `EmployeesServiceMap.ts`
-   🧪 Comprehensive test coverage for all service methods

---

## 🏗️ Architecture Overview

```
Registry → EmployeesServiceSqlite → AbstractEmployeesServiceSql → SQLite (via Knex)
```

This layered design separates abstraction from implementation, ensuring scalability and easy migration to other databases (e.g., PostgreSQL, MySQL).

---

## 🔍 How It Works

1. The `AbstractEmployeesServiceSql` class defines method signatures for all SQL operations.
2. The subclass `EmployeesServiceSqlite` provides real implementations using Knex.
3. All data operations interact directly with the SQLite database.
4. Unit tests verify CRUD behavior and database consistency.

**Implemented methods:**

-   `getAll()` → Returns all employees or filters by department
-   `getById(id)` → Finds an employee by ID
-   `addEmployee(employee)` → Inserts a new employee record
-   `updateEmployee(id, data)` → Updates an employee’s fields
-   `deleteEmployee(id)` → Deletes an employee by ID

---

## 📜 Output Example

**Example: Fetching All Employees**

```ts
const employees = await employeesService.getAll();
console.log(employees);
```

**Output:**

```json
[
	{
		"id": "f1a2b3c4-5678-90ab-cdef-1234567890ab",
		"fullName": "Alice Johnson",
		"avatar": "https://example.com/avatar.jpg",
		"department": "Development",
		"birthDate": "1995-05-20",
		"salary": 12000
	},
	{
		"id": "b2c3d4e5-6789-01ab-cdef-234567890abc",
		"fullName": "Bob Smith",
		"avatar": "https://example.com/avatar2.jpg",
		"department": "QA",
		"birthDate": "1990-03-15",
		"salary": 10000
	}
]
```

---

## 📦 Usage

1. Clone the repository:

```bash
git clone https://github.com/malikinss/telran-backend-hw13.git
cd telran-backend-hw13
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables (if needed):

```env
DB_PATH=./data/employees.db
```

4. Run the SQLite service tests:

```bash
npm run test-service sqlite
```

All tests must pass to confirm correct implementation.

---

## 🚀 Usage Examples (HTTP)

While this homework focuses on the **service layer**, it powers the following REST endpoints:

| Method   | Endpoint             | Description            |
| -------- | -------------------- | ---------------------- |
| `GET`    | `/api/employees`     | Retrieve all employees |
| `GET`    | `/api/employees/:id` | Retrieve one employee  |
| `POST`   | `/api/employees`     | Create a new employee  |
| `PATCH`  | `/api/employees/:id` | Update employee data   |
| `DELETE` | `/api/employees/:id` | Remove an employee     |

---

## ✅ Dependencies

-   `typescript` – Type safety and modern JS features
-   `knex` – SQL query builder
-   `sqlite3` – Embedded SQL database
-   `uuid` – Employee ID generation
-   `node:test` – Testing framework
-   `dotenv` – Environment variable management

---

## 📊 Project Status

✅ Completed
💯 All tests passed (`npm run test-service sqlite`)

---

## 📄 License

MIT License

---

## 🧮 Conclusion

This project demonstrates how to extend abstract classes to create real database services using **Knex** and **SQLite**.
You’ve learned how to implement database CRUD logic in a modular, testable, and maintainable way.
All tests passing confirms that your SQL service works correctly and integrates seamlessly with the rest of the backend system.

---

Made with ❤️ and `TypeScript` by **Sam-Shepsl Malikin** 🎓

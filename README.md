# Support Tickets 🛠️

A lightweight Node.js REST API for managing customer support tickets. Built using only native modules and custom utilities, this project allows full CRUD operations for support tickets, stored locally in a JSON file.

<br>

## ✨ Features

- Create new support tickets
- List all existing tickets
- Update ticket information and status
- Delete tickets
- Middleware for JSON body parsing and route handling
- No external frameworks – built with Node.js core modules

<br>

## 📁 Project Structure

- `support-tickets/`
   - `package.json`: Contains metadata about the project, such as name, version, and dependencies.
   - `src/`: Contains the main source code of the application.

     - **`server.js`**: Entry point of the server. It initializes the server, applies middlewares, and loads routes.

     - **`controllers/`**: Holds the logic for handling ticket operations.
       - **`tickets/`**
         - `create.js`: Handles the creation of new support tickets.
         - `index.js`: Retrieves and lists all support tickets.
         - `remove.js`: Deletes a specific support ticket.
         - `update.js`: Updates ticket data like title and description.
         - `updateStatus.js`: Changes the status of an existing ticket.

     - **`database/`**: Responsible for data persistence.
       - `database.js`: Provides helper functions to read/write data from/to the JSON database.
       - `db.json`: The actual database file storing all tickets in JSON format.

     - **`middlewares/`**: Custom middleware functions used by the server.
       - `jsonHandler.js`: Parses incoming requests with JSON payloads.
       - `routeHandler.js`: Handles custom routing logic for incoming HTTP requests.

     - **`routes/`**: Defines the API routes.
       - `index.js`: Exports all route configurations to be used in the server.
       - `tickets.js`: Defines routes related to ticket operations (GET, POST, PUT, DELETE).

     - **`utils/`**: Utility/helper functions.
       - `extractQueryParams.js`: Parses query parameters from URLs.
       - `parseRoutePath.js`: Matches and parses dynamic route paths (e.g., `/tickets/:id`).

<br>

## 🚀 Getting Started

1. Clone the repository

```bash
git clone https://github.com/eduardapontel/support-tickets.git
```

2. Install dependencies
```bash
npm install
```

3. Run the server
```bash
node src/server.js
```

The API will be running at ```http://localhost:3333```.

<br>

## 🔗 API Endpoints
| Method | Endpoint              | Description          |
| ------ | --------------------- | -------------------- |
| GET    | `/tickets`            | List all tickets     |
| POST   | `/tickets`            | Create a new ticket  |
| PUT    | `/tickets/:id`        | Update ticket data   |
| PATCH  | `/tickets/:id/status` | Update ticket status |
| DELETE | `/tickets/:id`        | Delete a ticket      |


All data is stored persistently in src/database/db.json.

<br>

## 🤝 Contributing 

Feel free to contribute to this project by submitting issues or pull requests. Your feedback and suggestions are always welcome!


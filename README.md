## Deleting User Details

A minimal, browser-based CRUD app for managing user details. It allows you to **create**, **read**, **update**, and **delete** user records (with a strong focus on the delete flow) backed by a simple REST API.

### Features

- **Add users**: Submit user details (username, email, phone) via a simple HTML form.
- **List users**: Fetch and render all existing users from the API.
- **Edit users**: Update previously created user details.
- **Delete users**: Permanently remove users from the backend via the API.
- **Persistent storage**: All operations are persisted through a REST API (CrudCrud).

### Tech Stack

- **HTML5** – basic layout and form.
- **Vanilla JavaScript** – DOM manipulation, event handling, and API integration.
- **Axios** – HTTP client for making API calls.
- **CrudCrud API** – disposable REST backend for demo purposes.

---

## Getting Started (for Devs)

### Prerequisites

- Any modern browser (Chrome, Firefox, Edge, Safari).
- Optional: A local static server (recommended for a more realistic setup).

### Setup & Run

1. **Clone the repo**

   ```bash
   git clone <your-repo-url>
   cd "Deleting User Details"
   ```

2. **Serve the app**

   You can either open `index.html` directly in the browser or use a simple static server (recommended):

   ```bash
   # Using Python
   python -m http.server 8000

   # Using Node.js (http-server)
   npx http-server

   # Using PHP
   php -S localhost:8000
   ```

3. **Open the app**

   - If using a server: go to `http://localhost:8000` in the browser.
   - If not using a server: double‑click `index.html` to open it directly.

---

## How to Use the App

- **Create / Add a user**
  - Fill in **Username**, **Email**, and **Phone No**.
  - Click **Submit**.
  - The new user appears in the list.

- **Edit a user**
  - Click **Edit** next to the desired user.
  - The form is pre‑populated with that user’s data.
  - Change the fields and click **Submit** to update.

- **Delete a user**
  - Click **Delete** next to the user.
  - The app sends a DELETE request to the API and removes the user from the UI.

---

## API Configuration

The app uses [CrudCrud](https://crudcrud.com/) as a temporary backend. The base URL is configured in `index.js`:

```javascript
const BASE_URL = "https://crudcrud.com/api/fd245f9d44cd4ff99c0ea4eb8dfb5e1f/appointmentData";
```

**Important for devs**:

CrudCrud URLs expire after some time. When that happens:

1. Go to [crudcrud.com](https://crudcrud.com/).
2. Generate a new API endpoint.
3. Replace the `BASE_URL` value in `index.js` with your new endpoint.

---

## Project Structure

```text
Deleting User Details/
├── index.html   # UI + form markup
├── index.js     # CRUD logic and API integration (Axios)
└── README.md    # Documentation
```

---

## Code Overview (High Level)

- **`handleFormSubmit(event)`**  
  Handles create/update submissions, reads values from the form, and sends the appropriate API request.

- **`displayUserOnScreen(userDetails)`**  
  Renders a user record to the DOM, wiring up **Edit** and **Delete** actions.

### API Endpoints Used

- **`GET /appointmentData`** – Fetch all users.
- **`POST /appointmentData`** – Create a new user.
- (Optionally, depending on implementation) **`DELETE /appointmentData/:id`** – Delete a specific user.

---

## Browser Support

Tested on:

- Chrome (latest)
- Firefox (latest)
- Edge (latest)
- Safari (latest)

---

## Roadmap / Possible Improvements

- [ ] Implement full **PUT/PATCH** for updates instead of workarounds.
- [ ] Add stricter client‑side validation (email/phone formats, required fields).
- [ ] Improve error handling and user‑facing messages.
- [ ] Show loading / empty states for better UX.
- [ ] Add consistent styling with a dedicated CSS file.
- [ ] Add confirmation prompts before delete.
- [ ] Extract API logic into a small service/module for easier testing.

---

## License

Open-source and available for learning and experimentation.

---

## Contributing

Pull requests and suggestions are welcome. If you improve the delete flow, validation, or error handling, feel free to open a PR.


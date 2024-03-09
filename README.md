## Simple Pastebin in Rust

**In main.rs**:

1. **Imports**: The code imports necessary modules and traits from Actix, Rusqlite, and other libraries to handle HTTP requests, database operations, and generate random tokens.

2. **Data Structures**: Defines a `FormData` struct to represent form data received from the client and an `AppState` struct to hold the database connection.

3. **Route Handlers**:
   - `index`: Handles GET requests to the root URL ("/") and returns the HTML content of the index page.
   - `submit`: Handles POST requests to "/submit" and inserts the submitted content into the database with a randomly generated token.
   - `get_paste`: Handles GET requests to "/paste/{token}" and retrieves the content associated with the provided token from the database.

4. **Database Operations**:
   - Opens or creates a SQLite database file named "pastes.db".
   - Creates a table named "pastes" if it does not exist, with columns for token (primary key) and content.

5. **Actix Web Server Configuration**:
   - Configures Actix web server routes for serving static files ("/style.css") and handling HTTP requests ("/", "/submit", "/paste/{token}").
   - Binds the server to the address "127.0.0.1:8080" and starts the server.

**In index.html**:

1. **Body Content**:
   - Displays the Rust mascot (Ferris) dancing as the logo.
   - Provides a heading indicating "Rust PasteBin" and a description of the application.
   - Presents a form for submitting content with a textarea and a submit button.

### Running the Application:
- To run the application, execute ```cargo run``` in the terminal.
- Access the application in a web browser by navigating to ```http://localhost:8080```.
- Enter the desired content in the textarea and click the "Submit" button to generate a URL for the paste.
- Share the generated URL with others to access the paste content.

### Sum up:
This Rust project demonstrates the implementation of a simple PasteBin application using Actix for web server functionality, Rusqlite for database operations, and HTML for the user interface. 
It allows users to submit text content, store it in a local database, and retrieve it using a generated URL. 
The provided HTML file defines the structure and design of the user interface, while the Rust code handles HTTP requests, database interactions, and URL routing.

#### Tips:
- To run the application: ```cargo run```
- Navigate to: ```http://localhost:8080```
- Enter your text content in the textarea and click "Submit"
- You will be redirected to a page displaying your paste token (you can share this with anyone ~ ok, this is localhost ~ but you get the idea)
- Use ```ctrl + c``` to end the program (kill the process)

Credits: [Akhil Sharma](https://github.com/AkhilSharma90)

## BookHolidays.com

### Project Title:
Full-Stack Hotel Booking Website

### Project Description:
This project is a comprehensive full-stack hotel booking website designed to provide users with a seamless booking experience. Key features include:

- **User Authentication:** Secure user registration and login functionalities ensure that user data and sessions are protected.
- **Hotel Booking:** Users can browse, select, and book hotels with ease, thanks to a well-designed booking system.
- **Search Functionality:** An intuitive search feature allows users to quickly find hotels based on their preferences and criteria.
- **Secure Card Payments:** Integrated secure payment gateway for processing card payments, ensuring transactions are safe and reliable.
- **Cookies Management:** Efficient cookies management to enhance user experience by remembering user preferences and session information.

## Backend Configuration

1. **Environment Files**: Navigate to the `backend` folder and create two files: `.env` and `.env.e2e`. Add the following contents to both files:

    ```plaintext
    MONGODB_CONNECTION_STRING=

    JWT_SECRET_KEY=
    FRONTEND_URL=

    # Cloudinary Variables
    CLOUDINARY_CLOUD_NAME=
    CLOUDINARY_API_KEY=
    CLOUDINARY_API_SECRET=

    # Stripe
    STRIPE_API_KEY=
    ```

2. **MongoDB Setup**: 
    - Sign up for an account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
    - Create a new cluster and follow the instructions to set up a new database.
    - Once set up, obtain your MongoDB connection string and add it to the `MONGODB_CONNECTION_STRING` variable in your `.env` files.
    - For the `.env.e2e` setup see "running automated tests" below

3. **Cloudinary Setup**:
    - Create an account at [Cloudinary](https://cloudinary.com/).
    - Navigate to your dashboard to find your cloud name, API key, and API secret.
    - Add these details to the respective `CLOUDINARY_*` variables in your `.env` files.

4. **Stripe Setup**:
    - Sign up for a Stripe account at [Stripe](https://stripe.com/).
    - Find your API keys in the Stripe dashboard.
    - Add your Stripe API key to the `STRIPE_API_KEY` variable in your `.env` files.
  
5. **JWT_SECRET_KEY**:
    - This just needs to be any long, random string. You can google "secret key generator".

7. **Frontend URL**:
    - The `FRONTEND_URL` should point to the URL where your frontend application is running (typically `http://localhost:3000` if you're running it locally).

## Frontend Configuration

1. **Environment Files**: Navigate to the `frontend` folder and create a file: `.env`:

    ```plaintext
    VITE_API_BASE_URL=
    VITE_STRIPE_PUB_KEY=
    ```

5. **VITE_API_BASE_URLL**:
    - The `VITE_API_BASE_URL` should point to the URL where your backend application is running (typically `http://localhost:7000` if you're running it locally).
  
  
  ## Running the Application

1. **Backend**:
    - Navigate to the `backend` directory.
    - Install dependencies: `npm install`.
    - Start the server: `npm start`.

2. **Frontend**:
    - Open a new terminal and navigate to the `frontend` directory.
    - Install dependencies: `npm install`.
    - Start the frontend application: `npm run dev`.
    - The application should now be running on `http://localhost:5173` but verify this in your command line terminal
  
  ## Running Automated Tests

1. **MongoDB Setup**: 
    - You will ideally want to create a new mongoDb database for your tests to run against. This is to keep the data stable 
    - Sign up for an account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
    - Create a new project (e.g e2e tests)
    - Create a new cluster and follow the instructions to set up a new database.
    - Once set up, obtain your MongoDB connection string and add it to the `MONGODB_CONNECTION_STRING` variable in your `.env.e2e` file.
      
2. **Importing Test Data into MongoDB**:

    - The repository contains a `data` folder at the root, which includes JSON files for a test user and a test hotel. You can import these into your MongoDB collections to quickly set up test data.
    - **Locate the Test User File**: In the `data` folder, find the file containing the test user data (likely named something like `test-users.json`).
    - **Open MongoDB Compass**: Launch MongoDB Compass and connect to your database.
    - **Select the Database**: In Compass, select the database you are using for the automated tests (created in step 1).
    - **Import User Data**:
        - Navigate to the `users` collection within your database. Create it if it doesn't exist
        - Click on the "Add Data" button and select "Import File".
        - Browse to the location of your `test-users.json` file and select it.
        - Choose JSON as the file format and click "Import".
        - The test user data will be added to the `users` collection.
        - user login: ghoraisaikat997@gmail.com/123456
    -  **Locate the Test Hotel File**:
        - Navigate to the `hotels` collection within your database. Create it if it doesn't exist
        - Repeat the import process as you did for the user data, but this time select the `test-hotel.json` file.
        - Ensure the file format is set to JSON and click "Import".
        - The test hotel data will be added to the `hotels` collection.
 
3. **Running tests**    
    - In VS Code install the [Playwright extension](https://marketplace.visualstudio.com/items?itemName=ms-playwright.playwright)
    - Navigate to the `e2e-tests` directory.
    - Install dependencies: `npm install`.
    - Start the frontend and backend server using the steps above
    - [Using the Playwright extension to run the tests](https://playwright.dev/docs/getting-started-vscode#running-tests)
  
## Deployment

To deploy this application using Render.com, follow these steps:

1. **Frontend Deployment:**
   - Navigate to the `frontend` directory.
   - Install the required dependencies:
     ```bash
     cd frontend
     npm install
     ```
   - Build the frontend application:
     ```bash
     npm run build
     ```

2. **Backend Deployment:**
   - Navigate to the `backend` directory.
   - Install the required dependencies:
     ```bash
     cd backend
     npm install
     ```
   - Start the backend server:
     ```bash
     npm start
     ```

### Notes:
- Ensure that you have configured Render.com with the appropriate build and start commands for both the frontend and backend services.
- Adjust the build and start commands if your project setup differs from the standard practices.


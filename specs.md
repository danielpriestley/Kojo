# Kojo Backend API Specifications

Create the backend for the Kojo app, allowing users to create, update, track and delete habits. The front-end and UI will be developed in the future after the basic functionality has been established. This specification is to be used as a reference for everything that will be implemented in the backend.

### Habits
- Create new Habit
    * User must be signed in
    * Habits must be assigned a category
    * Field validation via Mongoose
- Update Habit
    * Owner only
    * Can update name, count and category
    * Updates Habit values in database
- Delete Habit
    * Owner only
    * Removes Habit values in database
- Get Habit
    * Owner only
    * Fetch single habit from database
- Get all Habits
    * Owner only
    * Fetch all habits associated with user
- Get all Habits for Category
    * Owner only
    * Fetch all habits from a specific category

### Categories
- Create new Category
    * Category must be assigned a colour & name
    * User must be signed in
    * Field validation via Mongoose
- Update Category
    * Owner only
    * Can update name, colour
    * Updates values in database
- Delete Category
    * Owner only
    * Removes ONLY the Category
    * Associated habits moved to Unassigned Category
- Delete Category & Habits
    * Owner only
    * Removes the Category AND Habits associated with it
    * Removes Category and Habits from Database
- Get Category
    * Gets specific Category from database
    * Owner only
    * Gets a single Category from database
- Get All Categories
    * Owner Only
    * Gets all Categories from Database

### Users & Authentication
- Authentication will be done using JWT/Cookies
    * JWT and Cookie will expire in 30 days
- User Registration
    * Register only as 'User'
    * Once registered, token will be sent along with a cookie
    * Passwords will be hashed
- User Login
    * User can login with email and password
    * Plain text password will be compared with the stored hashed password
    * Once logged in, the token will be sent along with a cookie
- User Logout
    * Cookie will be sent to set token = none
- Get User
    * Route to get the currently logged in user (via token)
- Password Reset (lost password)
    * User can request to reset password
    * Hashed token will be emailed to the users registered email address
    * A put request can be made to the generated url to reset password
    * The token will expire after 10 minutes
- Update User Info
    * Authenticated user only
    * seperate route to update password
- User CRUD
    * Admin only
- Users can only be made admin by updating the database field manually

### Security
- Encrypt Passwords and reset tokens
- Prevent cross site scripting - XSS
- Prevent NoSQL injections
- Add a rate li it for requests of 100 requests per 10 minutes
- Protect against http param polution
- Add headers for security (helmet)

### Documentation
- Research various documentation solutions
- Alternatively use postman/docgen to generate documentation
- Add HTML files as the / route for the API

### Deployment (Digital Ocean)
- Push project to GitHub
- Create a droplet on DigitalOcean
- Clone repo on to the server
- Use PM2 process manager
- Enable firewall (ufw) and open needed ports
- Create an NGINX reverse proxy for port 80
- Connect a domain name
- Install an SSL using Let's Encrypt

## Extras
- Create NPM scripts for dev and production env
- Config file for important constants
- Use controller methods with documented descriptions/routes
- Error handling middleware from DevCamper project
- Authentication middleware for protecting routes
- Validation using Mongoose and no external libraries
- Use async/await
- Create a database seeder to import and destroy data
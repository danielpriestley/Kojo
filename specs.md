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
### Security
### Documentation
### Deployment (Digital Ocean)
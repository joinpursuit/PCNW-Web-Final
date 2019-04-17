# Comprehensive Technical Assessment - Practical

## Opening Remarks

This exam, like many exams before it, will be an **open-book, project-driven exam**.

- You are permitted the use of online resources, including your notes. 
- **You are not permitted to discuss the exam with your peers or to share code.** If you have questions, or would like to discuss details of the exam, please talk to an instructor or TA.
  - Instructors will explicitly look for similiar code. 
- You are welcome (encouraged, required) to utilize GitHub and Git for this exam. Until the conclusion of the exam period, please **make your repositories private** and invite the 5.2 staff as collaborators to your repo. 
  - mmosayed
  - mottaquikarim
  - Ceejaymar
  - Dinnall
  - susanahan
- As you continue to work through this project make regular commits because we will be monitoring your commit history for code consistency and educational integrity.
- Please have a single repository with the following folders:
  - `/backend`: Your express application
  - `/frontend`: Your react application


## TV Show Watchlist App

TV Show Watchlist will be a full-stack application where users can post, comment on, and favorite TV shows that they are binging on.

* The app does **not** need user authentication, and does not need passwords - only usernames. You can assume from the front end that your logged in user is whichever user ID from the database you wish to be the logged in user.
* Users should be able to **post shows** that they watch. These shows are shared on their profile pages.
* Users can view the profile pages of other users.
* Users should be able to **comment** on other users' shows. Comments should include the comment's text as well as the username of the user who posted the comment.

### Database Structure

The following tables and columns will be necessary:

- **Users**
  - id
  - username - *Unique*
- **Genres**
  - id
  - genre_name - *Unique*
- **Shows**
  - id
  - title
  - img_url
  - user_id - *References Users*
  - genre_id - *References Genres*
- **Comments**
  - id
  - comment_body
  - user_id - *References Users*
  - song_id - *References Songs*

#### You may use the included [seed.sql](/seed.sql) file.

### API Endpoints

Your API Endpoints should include at least:

- **Users**
  - GET all users
  - GET single user
  - POST new user
- **Genres**
  - GET all genres
- **Shows**
  - GET all shows
  - GET all shows for specific genre_id
  - GET all shows for specific user_id
  - GET one show
  - POST new show
- **Comments**
  - GET all comments for specific show_id
  - POST new comment

### Frontend

Your frontend must include the following routes/pages:

| Mockup | Feature |
| ---    | ---     |
| <img src='assets/Home.png' width='300'> | **`/` :** Home route. Should just welcome the user to the applciation. Must include Navbar, links, display message.
| <img src='assets/Users.png' width='300'> | **`/users` :** Shows master list of all users. Shows the "logged in" user. Should be able to click on each username linking to the user profile page.
| <img src='assets/User-Watching.png' width='300'> |  **`/user/:id` :** User profile page. Shows all the shows the user is watching. Must show the image, title, genre. Should be able to click on the show and take you to the show page. Each row should have TWO shows per row; note the mockup isn't reflecting that.
| <img src='assets/User-Post.png' width='300'> | **`/user/post` :** Shows a form where the logged in user can add a new show. Should be able to submit to the Database. These changes are reflected app wide. 
| <img src='assets/User-Show.png' width='300'> |  **`/show/:id` :** A specific show's profile page for a specific user. Shows the title, image, genre, number of comments and list of comments. Allows you to add new comments. The comment should be reflected immediately on the list without needing to refresh the page.
| <img src='assets/Shows.png' width='300'> |  **`/shows` :** Masterlist of all the shows. **Don't repeat the same show twice.** For each show list all the users who are watching. Clicking on the name of the user takes you to that specific users' show profile page. We are assuming that the name of the show has to match exactly to be considered the same show.

#### BONUS

Make it so that you can see all the users created in the database and select which one should be the logged in user. Allowing the person using the application to be able to navigate and switch between different logged in users.






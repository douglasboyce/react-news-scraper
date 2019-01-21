# REACT-NEWS-SCRAPER

A web app which allows users see recent New York Times Articles API and read the 10 resulting articles that render. Users have the option to save articles and commant about specifi articles as well. MongoDB persists the data. This app is built with the MERN stack.

## Motivation

To create an app for people wanting to read old and current news articles, and to do so utilizing MongoDB, Express.js, React.js, and Node.js.

## Tech/framework to be used

<b>Built with</b>
- [MongoDB](https://www.mongodb.com/)
- [Express.js](https://www.npmjs.com/package/express)
- [React.js](https://reactjs.org/)
- [Node.js](https://nodejs.org/en/)
- [Mongoose](http://mongoosejs.com/)
- [body-parser](https://www.npmjs.com/package/body-parser)
- [Bootstrap](https://getbootstrap.com/docs/3.3/)
- [Axios](https://github.com/axios/axios), 
- [React-Router](https://github.com/ReactTraining/react-router)
- HTML5, CSS3, Javascript(ES6)


## Steps to create app

1. I would use create-react-app tp create a new react app
2. remove the initial  code from the newly created app
3. Add a components folder
4. Create a Navbar component
    a. Add buttons for "Scrape New Article", "Save News Article", and "Show All Scraped News"
    b. Add the necessary events for each
    c. Add the routes associated with each button click
5. Create a Hero compoment with a image from the orginal news-scraper
6. Add functionality to the news scraper routers by adding database connectity and cherio to scrape the data.
7. The react-news-scraper, would be deployed to heroku.

## User Interactions

1. When the user selects "All Articles", it will show the top articles from the world news New York Times.
    a. This executes the route app.get("/scrape"), and perfoms a request from "https://www.nytimes.com/section/world".
    b.  It retrieves the "link, title, summary, and img (thumbnail) for all articles.
    c. If user selects "Save Article", for a specific article, this executes 'post("/save/:id"' This saves the specified article to the mongo database.
2. When the user selects "Saved Articles", it will show the articles which have been saved to the mongo database.
    a. This executes the route get("/saved"), and shows all articles which have been saved to the mongo database.
    b. It executes a "find", to locate all articles where the issaved is equal to true.
    b. If no articles, have been saved, "issaved = false", then a message is displayed "No articles have been saved."
3. When the user selects "Scrape for New Articles", it will show the current top articles.
4. When the user selects "Add a note", a pop-up (modal), is displayed.
    a. This allows the user to enter comments about a specific article
    b. If the user selects "Save", the note is saved to the mongo database.
    c. The route, post("/note/:id"), is executed and note.save, saves the note to the mongo database - Notes, by articles Id.
    d. After execution, the modal is closed and the user is returned to main screen.
    c. If the user selects "Cancel", no articles is saved and the user is returned to the main screen.

# ValueBlog

This is an admin controlled full stack MERN blog web application. Only admin has access to add, update & delete new blog post. Rich text editor feature enables us to edit text & add hyperlinks, images, videos etc. This project is hosted live on https://mern-valueblog.herokuapp.com/

Login Name- Your name <br />
Admin Password- projectqwerty

Project Specifications-
- Fully responsive web application.
- Displays all published blog posts on home page with author, date & time of blog post creation.
- Only admin can create/update/delete any blog post with full rich text editor features.
- Users can see all blog posts in chronological order on the home screen.

# Demo

  ![ezgif com-gif-maker (3)](https://user-images.githubusercontent.com/87348490/152381000-5f57b062-377c-48e2-acbc-ec0778422159.gif)

## Technologies Used

<a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a>
<a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> 
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> 
<a href="https://www.mongodb.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="40" height="40"/> </a>
<a href="https://expressjs.com" target="_blank" rel="noreferrer"> <img src="https://i.ibb.co/ckPHbQm/express-facebook-share.png" alt="express" width="60" height="40"/> </a>
<a href="https://reactjs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/> </a>
<a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/> </a> 
<a href="https://postman.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/getpostman/getpostman-icon.svg" alt="postman" width="40" height="40"/> </a>
<a href="https://heroku.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/heroku/heroku-icon.svg" alt="heroku" width="40" height="40"/> </a> 

## Google Lighthouse webpage perfomance report 

The full report can be accessed at https://drive.google.com/file/d/1FjAHQKGxpaWNOnO-fvSuU2OLNjnIS3re/view?usp=sharing
  
![valueblog](https://user-images.githubusercontent.com/87348490/152341465-c7c99654-58b2-4da9-983a-435329e71771.png)

## Lessons Learned

- Used ReactQuill for text editing and adding images & video links to the content of the blog.
- Designed routes using react-router-dom.
- Learnt to test CRUD operations using Postman.
- Deployed the full stack web app on Heroku using Git commands.

## Known Issues

- Rich Text Editor has text color & text background color feature working but the color palette is showing a single color throughout the palette. This is due to CSS color properties set in the root class which has taken precedence over the local properties.

## New Features to be added in Future

- Allow guest users to create account.
- Add search bar with filter to find a desired blog post.
- Add tags to blogs and allow users to comment and upvote the blog post.
- Add sharing options to share blog post on social media.

## Authors

[@mayankdrvr](https://www.github.com/mayankdrvr)

## Run on Local System

- Go to Code->Download ZIP to download the .zip file. Just extract the .zip file and open the extracted folder in VS Code editor.
- Open a new terminal in VS Code in the root(../../mern-blog-main/) folder.
- To install client libraries & dependencies and run the frontend, run the following commands 
```bash
  cd client
  npm install
  npm start
```
- To install server libraries & dependencies and run the backend, run the following commands 
```bash
  cd server
  npm install
  npm start
```
- Open http://localhost:3000/ to find the project running in your browser.

## Deployment on Heroku
The web app frontend & backend will be deployed in two separate apps on Heroku. Frontend will have the backend api in its Config Vars on Heroku. So, two apps are created on Heroku, one for frontend and one for backend.
### Deploying server folder
- Ensure that server folder has .gitignore file with .env & node_modules added to avoid these files to be pushed on hosting provider server.
- Create a Heroku account and create two new apps on it, one for the client and one for the server. Go to app settings and in Config Vars add your MongoDB database link along with jwt secret key and login screen password=qwerty.
```bash
  DATABASE=<Your mongoDB database link>
  JWT_SECRET=<Your jwt secret key>
  PASSOWRD=qwerty
```
- Install Heroku CLI & create a file named Procfile in the server folder with the following contents-
```bash
  web: node server.js
```
- Login to Heroku in terminal from client
```bash
  heroku login
```
- Browser will open with a Login button. Click the Login button to login to Heroku from command line and close the window.
- Go to the server folder and run the following commands one by one-
```bash
  git init
  git add .
  git commit -m "first commit"
  heroku git:remote -a <Name of the new app created by you on Heroku>
  git push heroku master
```
- Wait for a while for server folder files to deploy. If any error, then retry using 
```bash
  heroku ps:restart
```
- Find logs of any error using
```bash
  heroku logs --tail
```

### Deploying client folder
- Ensure that client folder has .gitignore file with .env & node_modules added to avoid these files to be pushed on the hosting provider server.
- Create a Heroku account and create a new app on it. Go to app settings and in Config Vars add the url of the heroku app created for the server above and add /api at the end of the URL(example https://abcdefghij.herokuapp.com/api). This tells the API location of your web app to Heroku. Add the follwing key value pair in Config Vars-
```bash
  REACT_APP_API=<URL of the deployed new app of server>/api
```
- Create a fie named Procfile in the client folder with the following contents-
```bash
  web: node server.js
```
- Login to Heroku in terminal from client
```bash
  heroku login
```
- Delete yarn.lock file.
- Run the following commands in the terminal opened in the client folder-
```bash
  git init
  git add .
  git commit -m "first commit"
  heroku git:remote -a <Name of the new app created for client side by you on Heroku>
  git push heroku master
  heroku open
```
- The full stack web app will be deployed and its link will open in your browser.

## License

[MIT](https://choosealicense.com/licenses/mit/)








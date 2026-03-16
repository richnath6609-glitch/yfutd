# Deployment Guide for Arima 111 Collections

Now that your application is using an Express backend and SQLite database, you can effortlessly deploy it to a live server.

## Recommended Platform: Render.com (Free & Easy)

1. **Push to GitHub**: 
   Ensure your entire `A111C` folder, including `package.json` and `server.js`, is pushed to a GitHub repository.
   
2. **Create a Render Account**: 
   Sign up at [render.com](https://render.com).

3. **Deploy a Web Service**:
   - Create a New **Web Service** on Render.
   - Connect it to your GitHub repository.
   - Set the Environment to **Node**.
   - **Build Command**: `npm install`
   - **Start Command**: `node server.js`

### A Warning About SQLite on Most Cloud Platforms:
Because platforms like Render, Vercel, and Heroku use *ephemeral file systems*, your SQLite databse file (`database.sqlite`) might get wiped every time they restart or re-deploy the server.

If you plan to use this in production to accept real orders, it is highly recommended to upgrade to a persistent database later, such as:
*   A managed **PostgreSQL** database (Render offers a free Postgres database exactly for this use case!).
*   **MongoDB Atlas**.

For now, the SQLite DB is perfect for testing all functionality on your local machine! You can continue developing locally until you are ready for a final permanent database setup.

To test locally right now:
Run `node server.js` inside this folder and open `http://localhost:3000`!

## Technologies Used

### Frontend:

- **React Ecosystem:**
  - Project was bootstrapped with **create-react-app**
  - UI-Layer was created with **React**
  - **React router** was used to implement client-side routing
  - State Management is handled with the **Context-API** (built into React core-library)
  - **Styled Components** were used to create all of the custom CSS
- Communication with the Backend is handled with **Axios** (REST-API) & **Socket.io** (Game logic)
- All localized strings and static page content (e.g. privacy policy) is stored in **Contentful** (cloud-based Headless-CMS) and retrieved via their Content Delivery API

### Backend:

- **Node.js** & **Express.js**
- **mongoDb** is used as the database & **mongoose** as ORM
- Authentication is implemented with **JSON Web Tokens**
  - Passwords are encrypted with **bcrypt**
- The client-server communication for the game-logic is implemented with **Socket.io**
- Uses **nodemailer** to send out transactional mails via Mailjet SMTP
- Security-packages included to make the application more robust are: **helmet**, **hpp**, **express-rate-limit** & **express-mongo-sanitize**

## Features

- User can register & login into the frontend application
  - Password is stored encrypted in DB (!)
  - Authentication is handled via JWT-webtokens to secure API-transactions & private routes
- Basic form of Virtual Gaming Currency
  - User gets a specific amount of VGC after registration, they can use this amount to play on any open table. Should their balance drop to zero they get the same starting amount again for free.
- App screens: Landing Page, Lobby (choose table etc.), Login Screen / Modal, Registration Screen / Modal, User Dashboard, Game UI
- User can join a table and play poker ⇒ full game-loop + In-game chat implemented, Functional animations to support visual gameplay experience
- Localization for two languages implemented (DE, EN)

## Quick Start

### Set-up MongoDB

Set-up either a local mongoDB instance or create a [cloud-hosted instance](https://www.mongodb.com/). Save your db username + passsword and the mongoDb connection-string as you will need it for the next step.

Please refer a "local.env" file in the "/server/config" folder with the following entries

### Add a ".env.local" file in the "/client" folder with the following entries

```
  REACT_APP_CONTENTFUL_SPACE_ID=<YOUR_CONTENTFUL_SPACE_ID>
  REACT_APP_CONTENTFUL_ACCESS_TOKEN=<YOUR_CONTENTFUL_ACCESS_TOKEN>
  REACT_APP_GOOGLE_ANALYTICS_TRACKING_ID=<YOUR_GOOGLE_ANALYTICS_TRACKING_ID>
  REACT_APP_SERVER_URI=<YOUR_BACKEND_URI_HOST_PORT>
```

### Install server dependencies

```bash
npm install
```

### Install client dependencies

```bash
cd client
npm install
```

### Run both Express & React from root project directory

```bash
npm run dev
```

### Build for production

```bash
cd client
npm run build
```

### Test production before deploy

```bash
NODE_ENV=production node server.js
```

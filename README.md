# Portfolio Website with MongoDB Atlas Integration

A modern, animated portfolio website with MongoDB Atlas backend integration for storing contact form submissions.

## Features

- ✨ Modern, animated UI with smooth transitions
- 📱 Fully responsive design
- 💾 MongoDB Atlas integration for contact form storage
- 🚀 Express.js backend API
- 📧 Contact form with database storage
- 🎨 Beautiful gradient animations

## Setup Instructions

### 1. Install Dependencies

```bash
npm install
```

### 2. MongoDB Atlas Setup

1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a free account or sign in
3. Create a new cluster (free tier is fine)
4. Create a database user:
   - Go to "Database Access" → "Add New Database User"
   - Choose "Password" authentication
   - Create a username and password (save these!)
5. Whitelist your IP address:
   - Go to "Network Access" → "Add IP Address"
   - Click "Allow Access from Anywhere" (for development) or add your specific IP
6. Get your connection string:
   - Go to "Database" → "Connect" → "Connect your application"
   - Copy the connection string
   - Replace `<password>` with your database user password
   - Replace `<dbname>` with your database name (e.g., `portfolio`)

### 3. Environment Variables

Create a `.env` file in the root directory:

```env
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/portfolio?retryWrites=true&w=majority
PORT=5000
```

**Important:** Replace the connection string with your actual MongoDB Atlas connection string.

### 4. Start the Server

For development (with auto-reload):
```bash
npm run dev
```

For production:
```bash
npm start
```

The server will run on `http://localhost:5000`

### 5. Open the Portfolio

Open `index.html` in your browser, or serve it using a local server.

**Note:** If you're opening `index.html` directly, you may need to update the `API_URL` in `script.js` to match your server URL, or use CORS-enabled browser settings.

## Project Structure

```
portfolio/
├── index.html          # Main HTML file
├── styles.css          # CSS styles and animations
├── script.js           # Frontend JavaScript
├── server.js           # Express server
├── package.json        # Dependencies
├── models/
│   └── Contact.js      # MongoDB Contact model
├── .env                # Environment variables (create this)
└── README.md           # This file
```

## API Endpoints

### POST `/api/contact`
Submit a contact form message.

**Request Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "subject": "Hello",
  "message": "Your message here"
}
```

**Response:**
```json
{
  "success": true,
  "message": "Thank you for your message! I will get back to you soon.",
  "data": {
    "id": "contact_id",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### GET `/api/contacts`
Get all contact submissions (for admin purposes).

### GET `/api/health`
Health check endpoint to verify server and database connection.

## Technologies Used

- **Frontend:** HTML5, CSS3, JavaScript
- **Backend:** Node.js, Express.js
- **Database:** MongoDB Atlas
- **ODM:** Mongoose

## Security Notes

- Never commit your `.env` file to version control
- Consider adding authentication for the `/api/contacts` endpoint in production
- Validate and sanitize all user inputs
- Use environment variables for sensitive data

## Troubleshooting

### Connection Issues

If you're having trouble connecting to MongoDB Atlas:

1. Check your connection string is correct
2. Verify your IP address is whitelisted
3. Ensure your database user has proper permissions
4. Check that your cluster is running (not paused)

### CORS Issues

If you encounter CORS errors, make sure:
- Your server is running
- The API_URL in `script.js` matches your server URL
- CORS is enabled in `server.js` (it is by default)

## License

ISC


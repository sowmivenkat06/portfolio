# Quick Setup Guide

## Step 1: Install Dependencies

```bash
npm install
```

## Step 2: Get MongoDB Atlas Connection String

1. Visit https://www.mongodb.com/cloud/atlas
2. Sign up or log in
3. Create a free cluster
4. Create a database user (Database Access → Add New Database User)
5. Whitelist IP: Network Access → Add IP Address → Allow Access from Anywhere
6. Get connection string: Database → Connect → Connect your application
7. Copy the connection string

## Step 3: Create .env File

Create a file named `.env` in the root directory with:

```
MONGODB_URI=mongodb+srv://YOUR_USERNAME:YOUR_PASSWORD@cluster.mongodb.net/portfolio?retryWrites=true&w=majority
PORT=5000
```

**Replace:**
- `YOUR_USERNAME` with your MongoDB username
- `YOUR_PASSWORD` with your MongoDB password
- `cluster` with your actual cluster name

## Step 4: Start the Server

```bash
npm start
```

Or for development with auto-reload:

```bash
npm run dev
```

## Step 5: Test the Connection

Visit: http://localhost:5000/api/health

You should see:
```json
{
  "status": "healthy",
  "database": "connected",
  "timestamp": "..."
}
```

## Step 6: Open Your Portfolio

Open `index.html` in your browser and test the contact form!

---

**Need Help?** Check the full README.md for detailed instructions.


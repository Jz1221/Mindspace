# Mindspace Chat Application

Mindspace is a real-time chat app where every message is a memory orb shared across web and mobile. Like Inside Out, your ideas and emotions flow seamlessly through the app, connecting people instantly and keeping your digital mind vibrant and alive.

## Features

- **Real-time Messaging**: Instant message delivery using Socket.io
- **Authentication**: Secure user authentication with Clerk
- **Cross-Platform**: Web, iOS, and Android support
- **Modern UI**: Clean and responsive interfaces built with React and NativeWind
- **Database**: MongoDB for data persistence
- **Containerized**: Docker support for easy deployment

## Tech Stack

### Backend
- **Runtime**: Bun
- **Framework**: Express.js with TypeScript
- **Database**: MongoDB with Mongoose
- **Authentication**: Clerk
- **Real-time**: Socket.io
- **CORS**: Enabled for cross-origin requests

### Mobile App
- **Framework**: React Native with Expo
- **Navigation**: Expo Router
- **Styling**: NativeWind (Tailwind CSS for React Native)
- **State Management**: Zustand
- **HTTP Client**: Axios
- **Real-time**: Socket.io Client

### Web App
- **Build Tool**: Vite
- **Framework**: React
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios
- **Real-time**: Socket.io Client

## Prerequisites

- **Node.js** (v18 or higher) or **Bun**
- **MongoDB** (local or cloud instance)
- **Clerk Account** (for authentication)
- **Expo CLI** (for mobile development)
- **Docker** (optional, for containerized deployment)

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd mindspace
   ```

2. **Install dependencies for each part**

   **Backend:**
   ```bash
   cd backend
   bun install
   ```

   **Mobile:**
   ```bash
   cd ../mobile
   npm install
   ```

   **Web:**
   ```bash
   cd ../web
   npm install
   ```

## Environment Setup

Create environment files for each component:

### Backend (.env)
```env
CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
MONGODB_URI=your_mongodb_connection_string
PORT=3000
NODE_ENV=development
```

### Mobile (.env)
```env
EXPO_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
EXPO_PUBLIC_API_URL=http://localhost:3000
```

### Web (.env)
```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_API_URL=http://localhost:3000
```

## Running the Application

### Development

1. **Start the Backend:**
   ```bash
   cd backend
   bun run dev
   ```
   The backend will run on http://localhost:3000

2. **Start the Web App:**
   ```bash
   cd web
   npm run dev
   ```
   The web app will run on http://localhost:5173

3. **Start the Mobile App:**
   ```bash
   cd mobile
   npm start
   ```
   Use Expo Go app or run on emulator/simulator

### Production

Use Docker to build and run the application:

```bash
# Build the Docker image
docker build -t mindspace .

# Run the container
docker run -p 3000:3000 \
  -e CLERK_PUBLISHABLE_KEY=your_key \
  -e VITE_CLERK_PUBLISHABLE_KEY=your_key \
  -e VITE_API_URL=http://localhost:3000 \
  mindspace
```

The application will be available at http://localhost:3000

## Project Structure

```
mindspace/
├── backend/          # Express.js API server
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── middleware/
│   │   └── utils/
│   ├── package.json
│   └── tsconfig.json
├── mobile/           # React Native app
│   ├── app/
│   ├── components/
│   ├── hooks/
│   ├── lib/
│   └── package.json
├── web/              # React web app
│   ├── src/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── lib/
│   │   └── pages/
│   ├── public/
│   └── package.json
├── Dockerfile
└── README.md
```

## API Endpoints

### Authentication
- `POST /auth/*` - Clerk authentication routes

### Users
- `GET /users` - Get all users
- `GET /users/:id` - Get user by ID

### Chats
- `GET /chats` - Get user's chats
- `POST /chats` - Create new chat
- `GET /chats/:id` - Get chat by ID

### Messages
- `GET /messages/:chatId` - Get messages for a chat
- `POST /messages` - Send new message

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

### This project is part of the Mindspace repository.

## Support

For support, you can contact me at:
- GitHub: jz1221

I’ll make sure your ideas and memories keep flowing smoothly!

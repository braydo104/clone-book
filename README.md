# CloneBook - Social Media Application

A full-featured social media platform built with Node.js, MongoDB, and Next.js.

## Features

- ✅ User registration and authentication with JWT
- ✅ User profiles with bios and profile pictures
- ✅ Create and share posts/updates
- ✅ Like and comment on posts
- ✅ Friend/connection system with requests
- ✅ Feed timeline showing posts from friends
- ✅ Direct messaging between users
- ✅ Notifications (likes, comments, friend requests, etc.)
- ✅ Search functionality for users
- ✅ Media uploads support

## Tech Stack

**Backend:**
- Node.js with Express.js
- MongoDB with Mongoose
- JWT Authentication
- TypeScript

**Frontend:**
- Next.js 14
- React 18
- Tailwind CSS
- Zustand for state management
- Axios for API calls

**DevOps:**
- Docker & Docker Compose

## Getting Started

### Prerequisites

- Docker and Docker Compose installed
- Node.js 18+ (for local development)
- MongoDB (or use Docker)

### Installation with Docker

1. Clone the repository
2. Navigate to the project directory
3. Create a `.env` file in the root directory (optional):
   ```
   MONGO_URI=mongodb://mongo:27017/clonebook
   JWT_SECRET=your_jwt_secret_key
   ```

4. Start the application:
   ```bash
   docker-compose up
   ```

5. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - MongoDB: mongodb://localhost:27017

### Local Development Setup

**Backend:**
```bash
cd backend
npm install
npm run dev
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

### Posts
- `POST /api/posts` - Create post
- `GET /api/posts/feed` - Get feed
- `GET /api/posts/:id` - Get post details
- `POST /api/posts/:id/like` - Like post
- `POST /api/posts/:id/comment` - Comment on post
- `DELETE /api/posts/:id` - Delete post

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update profile
- `POST /api/users/:id/friend-request` - Send friend request
- `POST /api/users/:id/accept-friend` - Accept friend request
- `GET /api/users/search/:query` - Search users

### Messages
- `POST /api/messages` - Send message
- `GET /api/messages/:userId` - Get messages with user
- `GET /api/messages/conversations/all` - Get all conversations

### Notifications
- `GET /api/notifications` - Get all notifications
- `PUT /api/notifications/:id` - Mark notification as read
- `PUT /api/notifications/mark/all-read` - Mark all as read

## Project Structure

```
clone book/
├── backend/
│   ├── src/
│   │   ├── models/
│   │   │   ├── User.ts
│   │   │   ├── Post.ts
│   │   │   ├── Comment.ts
│   │   │   ├── Message.ts
│   │   │   └── Notification.ts
│   │   ├── routes/
│   │   │   ├── auth.ts
│   │   │   ├── posts.ts
│   │   │   ├── users.ts
│   │   │   ├── messages.ts
│   │   │   └── notifications.ts
│   │   ├── middleware/
│   │   │   └── auth.ts
│   │   └── index.ts
│   ├── Dockerfile
│   └── package.json
├── frontend/
│   ├── app/
│   │   ├── auth/
│   │   │   ├── login/
│   │   │   └── signup/
│   │   ├── profile/
│   │   ├── messages/
│   │   ├── friends/
│   │   ├── notifications/
│   │   ├── store/
│   │   └── page.tsx
│   ├── components/
│   │   ├── Header.tsx
│   │   ├── PostCard.tsx
│   │   └── UserCard.tsx
│   ├── Dockerfile
│   └── package.json
└── docker-compose.yml
```

## Usage

1. **Sign Up**: Create a new account
2. **Create Posts**: Share your thoughts with the community
3. **Add Friends**: Send friend requests and connect with others
4. **Like & Comment**: Interact with posts from your friends
5. **Message**: Send direct messages to your friends
6. **Notifications**: Stay updated with all activities

## Environment Variables

```env
# Backend
MONGO_URI=mongodb://mongo:27017/clonebook
JWT_SECRET=your_jwt_secret_key
PORT=5000

# Frontend
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

## Future Enhancements

- [ ] Real-time notifications with WebSocket
- [ ] Image and video uploads to cloud storage (AWS S3)
- [ ] Groups and community features
- [ ] Stories feature
- [ ] Video calls using WebRTC
- [ ] Trending posts and hashtags
- [ ] User verification badges
- [ ] Advanced privacy settings
- [ ] Block and report functionality
- [ ] Dark mode

## License

ISC

## Support

For issues or feature requests, please open an issue on the GitHub repository.

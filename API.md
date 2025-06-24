# ConnectPro API Documentation

This document provides comprehensive documentation for the ConnectPro API endpoints.

## Base URL
```
http://localhost:5000/api
```

## Response Format
All API responses follow this standard format:

### Success Response
```json
{
  "data": {...}, // Requested data
  "status": 200
}
```

### Error Response
```json
{
  "message": "Error description",
  "status": 400|404|500
}
```

## Authentication
Currently, the API does not require authentication. This is planned for future implementation.

## Endpoints

### Profiles

#### Get All Profiles
Retrieve all profiles with optional filtering.

```http
GET /api/profiles
```

**Query Parameters:**
- `search` (string, optional): Search term for name, title, bio, or skills
- `industry` (string, optional): Filter by industry (technology, finance, healthcare, marketing, design)
- `level` (string, optional): Filter by experience level (senior, junior)

**Example Request:**
```http
GET /api/profiles?search=react&industry=technology&level=senior
```

**Example Response:**
```json
[
  {
    "id": 1,
    "name": "Sarah Chen",
    "title": "Senior Product Manager",
    "bio": "Passionate about building user-centric products...",
    "email": "sarah.chen@example.com",
    "avatar": "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d",
    "level": "senior",
    "industry": "technology",
    "skills": ["Product Strategy", "User Research", "Leadership"],
    "experience": "8 years exp."
  }
]
```

#### Get Profiles by Level
Retrieve profiles filtered by experience level.

```http
GET /api/profiles/level/:level
```

**Path Parameters:**
- `level` (string, required): Experience level ("senior" or "junior")

**Example Request:**
```http
GET /api/profiles/level/senior
```

**Example Response:**
```json
[
  {
    "id": 1,
    "name": "Sarah Chen",
    "title": "Senior Product Manager",
    "bio": "Passionate about building user-centric products...",
    "email": "sarah.chen@example.com",
    "avatar": "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d",
    "level": "senior",
    "industry": "technology",
    "skills": ["Product Strategy", "User Research", "Leadership"],
    "experience": "8 years exp."
  }
]
```

#### Get Single Profile
Retrieve a specific profile by ID.

```http
GET /api/profiles/:id
```

**Path Parameters:**
- `id` (number, required): Profile ID

**Example Request:**
```http
GET /api/profiles/1
```

**Example Response:**
```json
{
  "id": 1,
  "name": "Sarah Chen",
  "title": "Senior Product Manager",
  "bio": "Passionate about building user-centric products...",
  "email": "sarah.chen@example.com",
  "avatar": "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d",
  "level": "senior",
  "industry": "technology",
  "skills": ["Product Strategy", "User Research", "Leadership"],
  "experience": "8 years exp."
}
```

#### Create Profile
Create a new professional profile.

```http
POST /api/profiles
```

**Request Body:**
```json
{
  "name": "John Doe",
  "title": "Frontend Developer",
  "bio": "Passionate about creating amazing user experiences...",
  "email": "john.doe@example.com",
  "level": "junior",
  "industry": "technology",
  "skills": ["JavaScript", "React", "CSS"],
  "experience": "2 years exp.",
  "avatar": "https://example.com/avatar.jpg"
}
```

**Required Fields:**
- `name` (string): Full name
- `title` (string): Professional title
- `bio` (string): Professional bio/description
- `email` (string): Email address
- `level` (string): Experience level ("senior" or "junior")
- `industry` (string): Industry category
- `skills` (array): Array of skill strings
- `experience` (string): Years of experience

**Optional Fields:**
- `avatar` (string): Profile image URL

**Example Response:**
```json
{
  "id": 7,
  "name": "John Doe",
  "title": "Frontend Developer",
  "bio": "Passionate about creating amazing user experiences...",
  "email": "john.doe@example.com",
  "avatar": "https://example.com/avatar.jpg",
  "level": "junior",
  "industry": "technology",
  "skills": ["JavaScript", "React", "CSS"],
  "experience": "2 years exp."
}
```

#### Update Profile
Update an existing profile.

```http
PUT /api/profiles/:id
```

**Path Parameters:**
- `id` (number, required): Profile ID

**Request Body:**
Any subset of profile fields to update.

**Example Request:**
```json
{
  "title": "Senior Frontend Developer",
  "experience": "5 years exp.",
  "level": "senior"
}
```

**Example Response:**
```json
{
  "id": 7,
  "name": "John Doe",
  "title": "Senior Frontend Developer",
  "bio": "Passionate about creating amazing user experiences...",
  "email": "john.doe@example.com",
  "avatar": "https://example.com/avatar.jpg",
  "level": "senior",
  "industry": "technology",
  "skills": ["JavaScript", "React", "CSS"],
  "experience": "5 years exp."
}
```

### Connections

#### Create Connection
Send a connection request between two profiles.

```http
POST /api/connections
```

**Request Body:**
```json
{
  "fromProfileId": 1,
  "toProfileId": 2,
  "message": "I'd like to connect for mentorship opportunities."
}
```

**Required Fields:**
- `fromProfileId` (number): ID of the profile sending the request
- `toProfileId` (number): ID of the profile receiving the request

**Optional Fields:**
- `message` (string): Personalized connection message

**Example Response:**
```json
{
  "id": 1,
  "fromProfileId": 1,
  "toProfileId": 2,
  "message": "I'd like to connect for mentorship opportunities.",
  "status": "pending"
}
```

#### Get Profile Connections
Retrieve all connections for a specific profile.

```http
GET /api/profiles/:id/connections
```

**Path Parameters:**
- `id` (number, required): Profile ID

**Example Response:**
```json
[
  {
    "id": 1,
    "fromProfileId": 1,
    "toProfileId": 2,
    "message": "I'd like to connect for mentorship opportunities.",
    "status": "pending"
  },
  {
    "id": 2,
    "fromProfileId": 3,
    "toProfileId": 1,
    "message": "Looking for guidance in product management.",
    "status": "accepted"
  }
]
```

#### Update Connection Status
Update the status of a connection request.

```http
PUT /api/connections/:id
```

**Path Parameters:**
- `id` (number, required): Connection ID

**Request Body:**
```json
{
  "status": "accepted"
}
```

**Valid Status Values:**
- `pending`: Initial status when connection is created
- `accepted`: Connection request accepted
- `rejected`: Connection request rejected

**Example Response:**
```json
{
  "id": 1,
  "fromProfileId": 1,
  "toProfileId": 2,
  "message": "I'd like to connect for mentorship opportunities.",
  "status": "accepted"
}
```

## Error Codes

### 400 Bad Request
- Invalid request data
- Missing required fields
- Invalid enum values (level, status)

### 404 Not Found
- Profile not found
- Connection not found

### 500 Internal Server Error
- Database errors
- Unexpected server errors

## Rate Limiting
Currently no rate limiting is implemented. This is planned for future releases.

## Data Types

### Profile Object
```typescript
interface Profile {
  id: number;
  name: string;
  title: string;
  bio: string;
  email: string;
  avatar: string | null;
  level: "senior" | "junior";
  industry: string;
  skills: string[];
  experience: string;
}
```

### Connection Object
```typescript
interface Connection {
  id: number;
  fromProfileId: number;
  toProfileId: number;
  message: string | null;
  status: "pending" | "accepted" | "rejected";
}
```

## Examples

### cURL Examples

#### Get all senior technology professionals
```bash
curl "http://localhost:5000/api/profiles?level=senior&industry=technology"
```

#### Create a new profile
```bash
curl -X POST "http://localhost:5000/api/profiles" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Jane Smith",
    "title": "UX Designer",
    "bio": "Passionate about user-centered design...",
    "email": "jane.smith@example.com",
    "level": "junior",
    "industry": "design",
    "skills": ["Figma", "User Research", "Prototyping"],
    "experience": "2 years exp."
  }'
```

#### Send a connection request
```bash
curl -X POST "http://localhost:5000/api/connections" \
  -H "Content-Type: application/json" \
  -d '{
    "fromProfileId": 1,
    "toProfileId": 2,
    "message": "Would love to learn from your experience!"
  }'
```

### JavaScript Examples

#### Fetch profiles with filtering
```javascript
const response = await fetch('/api/profiles?search=react&level=senior');
const profiles = await response.json();
```

#### Create a new profile
```javascript
const newProfile = {
  name: "Alex Johnson",
  title: "Product Manager",
  bio: "Building products that users love...",
  email: "alex@example.com",
  level: "junior",
  industry: "technology",
  skills: ["Product Strategy", "Analytics"],
  experience: "3 years exp."
};

const response = await fetch('/api/profiles', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(newProfile),
});

const createdProfile = await response.json();
```

## Changelog

### v1.0.0 (Current)
- Initial API implementation
- Profile CRUD operations
- Connection management
- Search and filtering functionality
- In-memory storage implementation

### Planned Features
- Authentication and authorization
- Real-time notifications
- File upload for avatars
- Advanced search with Elasticsearch
- Rate limiting and API quotas
- Webhook support for connection events
# Backend with NodeJS and Express

## Installation
```
$npm install
```

## Testing
```
$npm test
```

## Running
```
$npm start
```

Access the API at `http://localhost:3000

## API testing
```
# Register a user (helper endpoint, not part of spec)
curl -X POST http://localhost:3000/api/register \
  -H "Content-Type: application/json" \
  -d '{"email":"demo@email.com","password":"password123"}'

# Login
curl -X POST http://localhost:3000/api/login \
  -H "Content-Type: application/json" \
  -d '{"email":"demo@example.com","password":"password123"}'
```
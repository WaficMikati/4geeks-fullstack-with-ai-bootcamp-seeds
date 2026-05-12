# Course Outline: JWT Authentication Implementation

**Title:** Mastering JWT Authentication with FastAPI and Secure Password Management
**Learnpack:** + Autenticando con JWT
**Prerequisite:** Seguridad de contraseñas en backend
**Target Audience:** Backend developers ready to implement secure authentication systems
**Total Lessons:** 12
**Format:** Mixed (17% hands-on)

---

## Course Description

This comprehensive course guides students through implementing JWT (JSON Web Token) authentication in FastAPI applications. Students will master the complete authentication flow, from understanding JWT structure to building secure endpoints with encrypted passwords and TinyDB storage. The course emphasizes security best practices, proper token lifecycle management, and frontend storage strategies.

By the end of this course, students will confidently build production-ready authentication systems that protect user credentials and manage secure sessions across web applications.

---

## Course Philosophy

This course emphasizes:
- **Security-first mindset**: Every decision prioritizes user data protection
- **Practical implementation**: Real FastAPI code that runs and produces observable results
- **Industry standards**: JWT best practices used in production environments
- **Human-in-the-loop**: Understanding concepts before implementing code

---

## Course Statistics Summary

| Section | Lessons |
|---------|---------|
| 00 - Welcome | 1 |
| 01 - JWT Fundamentals | 2 |
| 02 - Data Flow and Storage | 2 |
| 03 - Token Lifecycle Management | 2 |
| 04 - FastAPI JWT Implementation | 3 |
| 05 - Assessment and Mastery | 2 |
| 06 - Next Steps | 1 |
| **Total** | **12** |

---

## Section 00: Welcome

### 00.0 JWT Authentication Mastery Journey 📖

**Learning Objectives:**
- Understand why JWT authentication is the industry standard for modern web applications
- Recognize the security challenges this course solves
- Preview the complete authentication system you'll build
- Connect JWT concepts to your existing FastAPI and password security knowledge

**Content Outline:**
- The authentication challenge: Why basic auth isn't enough
- JWT as the solution: Stateless, scalable, secure
- Course journey preview: From theory to working FastAPI authentication
- Connection to previous learning: Building on encrypted passwords and FastAPI foundations

**Transitions:**
The next lesson dives deep into how JWT authentication flow works, starting with the request-response cycle that makes modern web authentication possible.

**Key Principles:**
- JWT enables stateless authentication across distributed systems
- Security requires understanding both theory and implementation
- Authentication and authorization work together but serve different purposes
- Modern applications demand scalable session management solutions

**Examples:**
- Comparing traditional session cookies vs JWT tokens in real applications
- Visualizing the difference between logging into a monolithic app vs microservices architecture
- Real-world scenario: User accessing protected resources across multiple API endpoints

---

## Section 01: JWT Fundamentals

### 01.0 Understanding JWT Authentication Flow 📖

**Learning Objectives:**
- Trace the complete JWT authentication request-response cycle
- Identify each participant in the authentication process (client, server, token)
- Distinguish between authentication and authorization in JWT context
- Analyze the stateless nature of JWT compared to traditional sessions

**Content Outline:**
- JWT authentication flow step-by-step: login request → credential validation → token generation → token response
- Request-response anatomy: What data travels in each direction
- Client-server interaction: How the browser and API communicate during authentication
- Stateless authentication: Why the server doesn't need to remember active sessions
- Authentication vs authorization distinction in JWT context

**Transitions:**
Now that you understand the authentication flow, the next lesson examines the internal structure of JWT tokens themselves—the three components that make this secure communication possible.

**Key Principles:**
- JWT authentication is a request-response cycle with clear data flows
- Stateless design means each request contains all necessary authentication information
- The server validates tokens without storing session state
- Authentication (who you are) precedes authorization (what you can access)

**Examples:**
- Step-by-step walkthrough: User login from browser click to API response
- Comparing JWT flow to traditional cookie-session authentication
- Real API requests: Showing actual HTTP headers and JSON payloads during authentication

**Anti-patterns (woven in):**
- **Treating JWT as sessions**: Unlike traditional sessions, JWT tokens should not be revoked server-side for normal logout—they expire naturally
- **Storing session state on server**: JWT's power comes from statelessness; maintaining server-side session data defeats the purpose

### 01.1 JWT Token Structure Deep Dive 📖

**Learning Objectives:**
- Decode and analyze each JWT component: Header, Payload, and Signature
- Understand the cryptographic role of each token segment
- Recognize what information belongs in JWT payload vs what should never be included
- Validate JWT structure and identify malformed tokens

**Content Outline:**
- JWT anatomy: Three Base64-encoded segments separated by dots
- Header: Algorithm and token type specifications
- Payload: Claims data including user information and expiration
- Signature: Cryptographic verification using secret key
- Base64 encoding: Why JWTs look like random strings but contain readable JSON
- Token validation process: How servers verify authenticity without contacting other services

**Transitions:**
Understanding JWT structure prepares us for the next section, where we'll explore how these tokens travel between client and server, and where clients should store them securely.

**Key Principles:**
- Each JWT segment serves a specific cryptographic purpose
- Payload data is encoded but not encrypted—anyone can read it
- Signature ensures token integrity and authenticity
- Secret key security is fundamental to JWT trustworthiness

**Examples:**
- Live JWT decoding: Taking a real token and examining each component
- Header examples: Different algorithms (HS256, RS256) and their use cases
- Payload examples: Standard claims (exp, iat, sub) and custom application data

**Anti-patterns (woven in):**
- **Sensitive data in payload**: Never include passwords, private keys, or confidential information in JWT payload—it's readable by anyone
- **Ignoring expiration claims**: Always validate `exp` claim; expired tokens should be rejected regardless of valid signature

---

## Section 02: Data Flow and Storage

### 02.0 Authentication Request-Response Cycle 📖

**Learning Objectives:**
- Map detailed HTTP request and response structures for JWT authentication
- Identify required headers, status codes, and data formats
- Understand error scenarios and appropriate API responses
- Design authentication endpoints that follow REST principles

**Content Outline:**
- Login endpoint anatomy: POST request structure, required fields, validation
- Success response: HTTP 200, JWT token delivery, user data inclusion
- Error responses: 401 (invalid credentials), 400 (malformed request), 422 (validation errors)
- Token usage in subsequent requests: Authorization header format
- Protected endpoint responses: How servers handle valid vs invalid tokens
- Request-response examples with actual HTTP structures

**Transitions:**
Once tokens are successfully delivered to the client, the next critical decision is where and how to store them securely in the browser environment.

**Key Principles:**
- HTTP status codes communicate authentication outcomes clearly
- Authorization header follows Bearer token convention
- Error responses should be informative but not reveal system details
- Consistent API response structure improves client integration

**Examples:**
- Complete HTTP request-response examples for login, token usage, and errors
- Headers analysis: Content-Type, Authorization, and security headers
- JSON response structures for success and various error scenarios

### 02.1 Frontend Token Storage Strategies 📖

**Learning Objectives:**
- Compare LocalStorage, SessionStorage, and HttpOnly cookies for JWT storage
- Evaluate security trade-offs and appropriate use cases for each storage method
- Implement secure token storage patterns in frontend applications
- Understand XSS and CSRF attack vectors related to token storage

**Content Outline:**
- LocalStorage: Persistent storage, XSS vulnerability, easy JavaScript access
- SessionStorage: Tab-scoped storage, automatic cleanup, same XSS concerns
- HttpOnly Cookies: Server-controlled, XSS protection, CSRF vulnerability
- Storage security comparison: Attack vectors and mitigation strategies
- Token lifecycle in each storage method: creation, access, and cleanup
- Best practices: When to use each approach based on application requirements

**Transitions:**
Proper storage sets the foundation for token lifecycle management, which we'll explore next—including how tokens expire and how applications handle revocation.

**Key Principles:**
- No storage method is perfect; each has specific security trade-offs
- HttpOnly cookies provide the best XSS protection but require CSRF mitigation
- LocalStorage offers convenience but demands careful XSS prevention
- Storage choice should match application security requirements and architecture

**Examples:**
- Code examples: Storing and retrieving tokens in each storage method
- Security comparison table: XSS vs CSRF vulnerability matrix
- Real-world scenarios: Single-page app vs traditional web app storage decisions

**Anti-patterns (woven in):**
- **Storing tokens in regular cookies**: Non-HttpOnly cookies are accessible to JavaScript and vulnerable to XSS attacks
- **Using LocalStorage without XSS protection**: Storing JWTs in LocalStorage requires comprehensive XSS prevention measures

---

## Section 03: Token Lifecycle Management

### 03.0 Token Revocation and Expiration 📖

**Learning Objectives:**
- Implement manual session cleanup and logout functionality
- Configure automatic token expiration with appropriate time limits
- Handle token refresh scenarios and graceful session management
- Design user experience for authentication state changes

**Content Outline:**
- Manual revocation: Client-side token cleanup during logout
- Automatic expiration: Setting appropriate `exp` claim values
- Token refresh patterns: When and how to issue new tokens
- Session timeout handling: User experience during token expiration
- Server-side considerations: Why JWT is stateless by design
- Cleanup strategies: Removing tokens from all storage locations

**Transitions:**
Token lifecycle management leads naturally to broader security considerations—the practices that keep JWT implementations secure in production environments.

**Key Principles:**
- Token expiration provides automatic security boundaries
- Manual cleanup prevents tokens from lingering after logout
- Short-lived tokens reduce security window but increase complexity
- User experience should gracefully handle authentication state changes

**Examples:**
- Logout implementation: Complete client-side token cleanup process
- Expiration handling: Detecting expired tokens and prompting re-authentication
- Refresh token patterns: Implementing seamless token renewal

### 03.1 JWT Security Best Practices 📖

**Learning Objectives:**
- Secure secret keys using environment variables and proper key management
- Validate JWT payload constraints and security boundaries
- Implement defense against common JWT attack vectors
- Design secure authentication flows that resist exploitation

**Content Outline:**
- Secret key management: Environment variables, rotation, and secure storage
- Payload security: What data to include vs exclude from JWT claims
- Token validation: Comprehensive server-side verification process
- Attack prevention: CSRF, XSS, and token replay attack mitigation
- Production considerations: Monitoring, logging, and incident response
- Security headers and HTTPS requirements for production deployment

**Transitions:**
With security foundations established, we're ready to implement these concepts in working FastAPI code, starting with the authentication infrastructure setup.

**Key Principles:**
- Secret key security is fundamental to JWT trustworthiness
- Defense in depth requires multiple security layers
- Security is an ongoing process, not a one-time configuration
- Production security demands monitoring and incident response capabilities

**Examples:**
- Environment variable configuration for secret keys
- Payload examples: Safe vs dangerous data inclusion decisions
- Security checklist: Complete production deployment verification

**Anti-patterns (woven in):**
- **Hard-coding secret keys**: Never embed SECRET_KEY in source code or commit to repositories—always use environment variables
- **Oversharing in payload**: Avoid including unnecessary user data, permissions lists, or sensitive information that increases token size and exposure risk

---

## Section 04: FastAPI JWT Implementation

### 04.0 Setting Up JWT Infrastructure 📖

**Learning Objectives:**
- Configure FastAPI project structure for JWT authentication
- Install and configure required JWT libraries and dependencies
- Set up environment variables and security configuration
- Create reusable authentication utilities and helper functions

**Content Outline:**
- Project structure: Organizing authentication modules and utilities
- Dependencies: PyJWT library installation and configuration
- Environment setup: SECRET_KEY, algorithm selection, and expiration settings
- Utility functions: Token generation, validation, and extraction helpers
- FastAPI security integration: Dependency injection patterns for authentication
- Configuration management: Centralized settings for authentication parameters

**Transitions:**
With infrastructure in place, the next lesson implements the core authentication endpoints where users log in and receive JWT tokens.

**Key Principles:**
- Modular architecture separates authentication concerns from business logic
- Configuration centralization enables easy environment-specific adjustments
- Dependency injection makes authentication reusable across endpoints
- Utility functions reduce code duplication and improve maintainability

**Examples:**
- Project folder structure with authentication modules
- Environment variable configuration examples
- FastAPI dependency injection patterns for JWT validation

### 04.1 Building Authentication Endpoints 💻

**Challenge Prompt:**
Build a complete FastAPI authentication system with login and registration endpoints that generate JWT tokens for valid users, encrypt passwords using bcrypt, and store user data in TinyDB.

**Solution Code:**
```python
from fastapi import FastAPI, HTTPException, Depends
from pydantic import BaseModel
import jwt
import bcrypt
from tinydb import TinyDB, Query
from datetime import datetime, timedelta
import os

app = FastAPI()
db = TinyDB('users.json')
User = Query()

SECRET_KEY = os.getenv("SECRET_KEY", "your-secret-key-here")
ALGORITHM = "HS256"

class UserCreate(BaseModel):
    username: str
    password: str

class UserLogin(BaseModel):
    username: str
    password: str

def create_token(username: str):
    payload = {
        "sub": username,
        "exp": datetime.utcnow() + timedelta(hours=24)
    }
    return jwt.encode(payload, SECRET_KEY, algorithm=ALGORITHM)

@app.post("/register")
def register(user: UserCreate):
    if db.search(User.username == user.username):
        raise HTTPException(status_code=400, detail="Username already exists")
    
    hashed_password = bcrypt.hashpw(user.password.encode('utf-8'), bcrypt.gensalt())
    db.insert({"username": user.username, "password": hashed_password.decode('utf-8')})
    
    token = create_token(user.username)
    return {"access_token": token, "token_type": "bearer"}

@app.post("/login")
def login(user: UserLogin):
    db_user = db.search(User.username == user.username)
    if not db_user or not bcrypt.checkpw(user.password.encode('utf-8'), db_user[0]['password'].encode('utf-8')):
        raise HTTPException(status_code=401, detail="Invalid credentials")
    
    token = create_token(user.username)
    return {"access_token": token, "token_type": "bearer"}
```

**Challenge Code:**
```python
from fastapi import FastAPI, HTTPException, Depends
from pydantic import BaseModel
import jwt
import bcrypt
from tinydb import TinyDB, Query
from datetime import datetime, timedelta
import os

app = FastAPI()
db = TinyDB('users.json')
User = Query()

SECRET_KEY = os.getenv("SECRET_KEY", "your-secret-key-here")
ALGORITHM = "HS256"

class UserCreate(BaseModel):
    username: str
    password: str

class UserLogin(BaseModel):
    username: str
    password: str

def create_token(username: str):
    # TODO: Create JWT token with username and 24-hour expiration
    pass

@app.post("/register")
def register(user: UserCreate):
    # TODO: Check if user exists, hash password, store in TinyDB, return JWT
    pass

@app.post("/login")
def login(user: UserLogin):
    # TODO: Validate credentials, verify password, return JWT
    pass
```

### 04.2 Protecting Routes with JWT Middleware 💻

**Challenge Prompt:**
Create FastAPI middleware that validates JWT tokens and protects routes, allowing only authenticated users to access protected endpoints while returning appropriate error responses for invalid tokens.

**Solution Code:**
```python
from fastapi import FastAPI, HTTPException, Depends, Header
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
import jwt
from typing import Optional

app = FastAPI()
security = HTTPBearer()

SECRET_KEY = os.getenv("SECRET_KEY", "your-secret-key-here")
ALGORITHM = "HS256"

def verify_token(credentials: HTTPAuthorizationCredentials = Depends(security)):
    try:
        payload = jwt.decode(credentials.credentials, SECRET_KEY, algorithms=[ALGORITHM])
        username = payload.get("sub")
        if username is None:
            raise HTTPException(status_code=401, detail="Invalid token")
        return username
    except jwt.ExpiredSignatureError:
        raise HTTPException(status_code=401, detail="Token has expired")
    except jwt.InvalidTokenError:
        raise HTTPException(status_code=401, detail="Invalid token")

@app.get("/protected")
def protected_route(current_user: str = Depends(verify_token)):
    return {"message": f"Hello {current_user}, you have access to protected data!"}

@app.get("/profile")
def get_profile(current_user: str = Depends(verify_token)):
    return {"username": current_user, "status": "authenticated"}

@app.get("/public")
def public_route():
    return {"message": "This is public data, no authentication required"}
```

**Challenge Code:**
```python
from fastapi import FastAPI, HTTPException, Depends, Header
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
import jwt
from typing import Optional

app = FastAPI()
security = HTTPBearer()

SECRET_KEY = os.getenv("SECRET_KEY", "your-secret-key-here")
ALGORITHM = "HS256"

def verify_token(credentials: HTTPAuthorizationCredentials = Depends(security)):
    # TODO: Decode JWT, validate expiration, return username or raise HTTPException
    pass

@app.get("/protected")
def protected_route(current_user: str = Depends(verify_token)):
    # TODO: Return protected data for authenticated user
    pass

@app.get("/profile")
def get_profile(current_user: str = Depends(verify_token)):
    # TODO: Return user profile information
    pass

@app.get("/public")
def public_route():
    return {"message": "This is public data, no authentication required"}
```

---

## Section 05: Assessment and Mastery

### 05.0 JWT Implementation Synthesis 📖

**Learning Objectives:**
- Integrate all JWT components into a cohesive authentication system
- Troubleshoot common JWT implementation issues and edge cases
- Optimize JWT implementation for production deployment considerations
- Evaluate security posture and identify potential vulnerabilities

**Content Outline:**
- Complete system integration: Connecting frontend storage with backend validation
- Error handling patterns: Graceful degradation and user experience during failures
- Performance considerations: Token size, validation speed, and scalability
- Security audit checklist: Comprehensive review of implementation security
- Production readiness: Monitoring, logging, and maintenance considerations
- Testing strategies: Unit tests, integration tests, and security testing approaches

**Transitions:**
This synthesis prepares you for the final assessment, where you'll demonstrate mastery of JWT authentication concepts and implementation patterns.

**Key Principles:**
- Complete authentication systems require both client and server components
- Error handling is crucial for security and user experience
- Production systems demand monitoring and maintenance planning
- Testing validates both functionality and security requirements

**Examples:**
- End-to-end authentication flow walkthrough with error scenarios
- Security checklist with specific validation points
- Production deployment considerations and monitoring setup

### 05.1 JWT Authentication Mastery Assessment 🧠

**Learning Objectives:**
- Demonstrate understanding of JWT structure and authentication flow
- Apply security best practices to real-world scenarios
- Analyze authentication implementation choices and trade-offs
- Troubleshoot JWT-related issues and security concerns

**Assessment Format:** Multiple Choice (7 questions)

**Question 1:**
Which JWT component ensures that the token hasn't been tampered with?
- A) Header - contains algorithm information
- B) Payload - contains user claims
- C) Signature - cryptographic verification
- D) Expiration - prevents old token usage

**Question 2:**
What is the most secure way to store JWT tokens in a browser-based application?
- A) LocalStorage with XSS protection measures
- B) SessionStorage for automatic cleanup
- C) HttpOnly cookies with CSRF protection
- D) Regular cookies for easy access

**Question 3:**
Which data should NEVER be included in a JWT payload?
- A) User ID and username
- B) Token expiration time
- C) User's hashed password
- D) User's role or permissions

**Question 4:**
How should JWT secret keys be managed in a production FastAPI application?
- A) Hard-coded in the source code for consistency
- B) Stored in environment variables and kept secure
- C) Included in the JWT payload for validation
- D) Generated dynamically on each server restart

**Question 5:**
What happens when a JWT token expires?
- A) The server automatically generates a new token
- B) The token becomes invalid and requests are rejected
- C) The user is permanently locked out of the system
- D) The token continues working but with limited permissions

**Question 6:**
Which HTTP status code should be returned for invalid JWT credentials during login?
- A) 400 Bad Request
- B) 401 Unauthorized
- C) 403 Forbidden
- D) 500 Internal Server Error

**Question 7:**
What is the primary advantage of JWT's stateless design?
- A) Tokens never expire automatically
- B) Server doesn't need to store session information
- C) Passwords don't need to be encrypted
- D) Frontend applications run faster

**Evaluation Criteria:**
- **7 correct:** JWT Authentication Expert - Complete mastery of concepts and security practices
- **5-6 correct:** JWT Practitioner - Strong understanding with minor gaps
- **3-4 correct:** JWT Learner - Basic concepts understood, needs additional practice
- **Below 3:** Review Required - Revisit core concepts before implementation

**Score Interpretation:**
This assessment validates your readiness to implement JWT authentication in production applications. Scores of 5+ indicate solid preparation for real-world authentication projects.

---

## Section 06: Next Steps

### 06.0 Your JWT Authentication Journey Ahead

**Content Outline:**
- **Course Recap:** You've mastered JWT structure, authentication flows, security best practices, and built working FastAPI authentication endpoints with encrypted passwords and TinyDB storage
- **Connection to Bigger Picture:** JWT authentication forms the foundation for advanced topics like OAuth integration, microservices authentication, and role-based authorization systems
- **Next Steps and Continued Learning:**
  - Advanced JWT patterns: Refresh tokens and token rotation strategies
  - OAuth 2.0 integration: "Login with Google" and third-party authentication
  - Role-based authorization: Implementing permissions and access control
  - Microservices authentication: JWT across distributed systems
- **Resources for Further Exploration:**
  - JWT.io for token debugging and validation
  - FastAPI Security documentation for advanced patterns
  - OWASP authentication guidelines for security best practices
  - Production JWT libraries and security tools
- **Encouragement and Celebration:** You've built the authentication foundation that powers modern web applications—from simple login systems to complex enterprise applications, JWT skills open doors to advanced backend development opportunities

**Note:** This is conclusion only - no theory, exercises, or assessment.

---
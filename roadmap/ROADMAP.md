# 📊 Study Group Platform - 16 Week Development Roadmap

**Project:** Centralized study group management platform  
**Duration:** 16 weeks (part-time, 2-3 hrs/day)  
**Approach:** TDD + Integration Testing + TypeScript Strict Mode  
**Tech Stack:** Node.js + Express + PostgreSQL + Redis + Kafka + Docker + GitHub Actions + AWS EC2

---

## **📌 Roadmap Overview**

| Phase | Weeks | Title | Focus | Tasks |
|-------|-------|-------|-------|-------|
| 1 | 1-2 | Foundation & CI/CD | Development environment, testing infrastructure, database schema | 10+ |
| 2 | 3-4 | Authentication & Authorization | Email/password auth, OAuth, RBAC, user management | 10+ |
| 3 | 5-6 | Groups & Sessions + Caching | Group/session management, attendance, read caching | 11+ |
| 4 | 7-8 | Notes & Cache Invalidation | Notes CRUD, search, smart cache invalidation | 10+ |
| 5 | 9-10 | Real-Time & Kafka | WebSockets, presence updates, event streaming | 11+ |
| 6 | 11-12 | Progress & Workers | Progress tracking, Kafka consumers, analytics | 10+ |
| 7 | 13-14 | AWS Deployment | EC2 setup, CI/CD integration, production readiness | 10+ |
| 8 | 15-16 | Optimization & Polish | Performance tuning, security audit, documentation | 10+ |

---

## **PHASE 1: Foundation & CI/CD Setup (Week 1-2)**

**Goals:**

- Production-like development environment with Docker
- GitHub Actions CI/CD pipeline
- Comprehensive testing infrastructure (TDD foundation)
- Complete database schema with relationships
- Express app skeleton
- JWT authentication utilities

### **Tasks**

#### **1.1: Project Initialization & Docker Setup**

**Goal:** Create local development environment that mimics production

**Approval Criteria:**

- [x] Node.js project initialized with proper TypeScript configuration
- [x] Dockerfile created for Node.js application
- [x] docker-compose.yml with services: App, PostgreSQL, Redis
- [x] .env.example documents all required variables
- [x] Hot-reloading configured for development
- [x] Git repository initialized with meaningful first commit
- [x] `docker-compose up` starts full stack successfully
- [x] All services healthy and accessible
- [x] TypeScript compiler configured (strict mode)

**Learning Topics:**

- Docker containerization
- docker-compose orchestration
- Environment variable management
- TypeScript project setup

---

#### **1.2: GitHub Actions CI/CD Pipeline**

**Goal:** Automated testing and quality checks on every commit

**Approval Criteria:**

- [ ] .github/workflows/ci.yml created with pipeline stages
- [ ] Lint stage: ESLint, Prettier check passes
- [ ] Test stage: Jest tests run successfully
- [ ] Build stage: Docker image builds without errors
- [ ] Security stage: npm audit runs (no critical vulnerabilities)
- [ ] Branch protection configured (require passing CI)
- [ ] Code coverage reports generated (target: >70%)
- [ ] CI pipeline runs in under 5 minutes
- [ ] Failed tests block PR merge

**Learning Topics:**

- GitHub Actions workflow syntax
- CI/CD pipeline design
- Code coverage tools
- Branch protection rules

---

#### **1.3: Testing Infrastructure & TDD Foundation**

**Goal:** Set up comprehensive testing framework for TDD approach

**Approval Criteria:**

- [ ] Jest installed and configured for TypeScript
- [ ] Test setup/teardown scripts working
- [ ] Test database (separate from development) created
- [ ] Test fixtures and factories implemented
- [ ] Test helpers reduce code duplication
- [ ] Code coverage tracking enabled (target: >80%)
- [ ] Example test file demonstrates TDD pattern
- [ ] Tests run in CI pipeline
- [ ] test:watch command for development

**Learning Topics:**

- Jest framework for TypeScript
- Test fixtures and factories
- TDD methodology
- Test database strategies

---

#### **1.4: Database Schema Design & Migrations**

**Goal:** Relational database design with all entities and relationships

**Approval Criteria:**

- [ ] PostgreSQL schema designed (10+ tables)
- [ ] All relationships defined: one-to-many, many-to-many
- [ ] Sequelize models created with TypeScript types
- [ ] Migration files (up/down) working
- [ ] Database seeders populate test data
- [ ] Foreign key constraints enforced
- [ ] NOT NULL and UNIQUE constraints applied
- [ ] Connection pooling configured
- [ ] Migrations runnable: `npm run migrate:up` and `:down`

**Learning Topics:**

- Relational database design
- PostgreSQL fundamentals
- Sequelize ORM with TypeScript
- Migrations and versioning

---

#### **1.5: Express App Skeleton & Middleware Stack**

**Goal:** Proper Express app structure with middleware pipeline

**Approval Criteria:**

- [ ] Express app initializes on port 3000
- [ ] Middleware ordered correctly: CORS → Body Parser → Logger → Routes → Errors
- [ ] Custom error classes created (ValidationError, AuthError, etc.)
- [ ] Winston logger configured for JSON output
- [ ] Request/response formatting consistent
- [ ] Global error handler catches exceptions
- [ ] 404 handler returns proper response
- [ ] No unhandled promise rejections
- [ ] Health check endpoint returns 200

**Learning Topics:**

- Express middleware architecture
- Middleware ordering
- Winston structured logging
- Error handling patterns

---

#### **1.6: JWT & Basic Authentication Setup**

**Goal:** Token-based authentication foundation

**Approval Criteria:**

- [ ] JWT utility functions: generateToken, verifyToken, decodeToken
- [ ] Password hashing with bcrypt implemented
- [ ] Auth middleware for protecting routes
- [ ] User model with password field
- [ ] Token expiry enforced (access: 1 hour)
- [ ] JWT secrets loaded from environment variables
- [ ] Passwords never stored plaintext
- [ ] Tests for JWT token generation/verification
- [ ] Token payload contains correct claims (userId, email, role)

**Learning Topics:**

- JWT fundamentals and best practices
- Password hashing with bcrypt
- Token-based authentication
- Secret management

---

#### **1.7: TypeScript Configuration & Types**

**Goal:** Strict TypeScript setup for entire project

**Approval Criteria:**

- [ ] tsconfig.json configured with strict mode
- [ ] Global type definitions created
- [ ] Database entity types defined
- [ ] API request/response types defined
- [ ] ESLint rules for TypeScript
- [ ] No implicit `any` allowed
- [ ] Strict null checks enabled
- [ ] Build command compiles to JS successfully

**Learning Topics:**

- TypeScript strict mode configuration
- Interface design
- Type inference
- Module resolution

---

#### **1.8: Logging & Monitoring Setup**

**Goal:** Structured logging for observability

**Approval Criteria:**

- [ ] Winston logger configured with JSON format
- [ ] Logs include: timestamp, level, context, requestId
- [ ] Request logger middleware captures all requests
- [ ] Error logs include stack traces
- [ ] Different log levels: info, warn, error, debug
- [ ] Logs output to console and file
- [ ] No console.log statements (use logger only)

**Learning Topics:**

- Winston logging library
- Structured logging
- Log levels and rotation

---

#### **1.9: Docker Compose Database Setup**

**Goal:** Database initialization with seeders

**Approval Criteria:**

- [ ] PostgreSQL starts with correct port (5432)
- [ ] Database created on startup
- [ ] Tables created from migrations
- [ ] Test data seeded
- [ ] Redis starts with correct port (6379)
- [ ] Volumes for persistent data configured
- [ ] Health checks for both services

**Learning Topics:**

- PostgreSQL Docker setup
- Volume management
- Docker health checks

---

#### **1.10: Git Workflow & Initial Commits**

**Goal:** Establish clean git history

**Approval Criteria:**

- [ ] .gitignore properly configured
- [ ] node_modules excluded
- [ ] .env files excluded
- [ ] Initial commit: project setup
- [ ] Commit messages follow convention
- [ ] README.md created with setup instructions
- [ ] No sensitive data committed
- [ ] Branch protection rules enabled

**Learning Topics:**

- Git workflow
- Commit message conventions
- .gitignore best practices

---

### **Phase 1 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met

---

---

## **PHASE 2: Authentication & Authorization (Week 3-4)**

**Goals:**

- Complete authentication system (email/password + OAuth)
- Role-based access control (RBAC)
- Secure password handling
- User profile management

### **Tasks**

#### **2.1: Email/Password Registration**

**Goal:** User registration with password validation

**Approval Criteria:**

- [ ] POST /auth/register endpoint created
- [ ] Email validation (format, uniqueness)
- [ ] Password strength validation (8+ chars, special char, number, uppercase)
- [ ] Password hashed before storage
- [ ] Duplicate email returns 409 Conflict
- [ ] Weak password returns 400 Bad Request
- [ ] User created in database
- [ ] Response includes accessToken and refreshToken
- [ ] Tests cover: valid registration, weak password, duplicate email

**Learning Topics:**

- Password validation rules
- Password hashing and salting
- Input validation
- HTTP status codes

---

#### **2.2: Email/Password Login**

**Goal:** User login and JWT token generation

**Approval Criteria:**

- [ ] POST /auth/login endpoint created
- [ ] User found by email
- [ ] Password verification against hash
- [ ] Invalid credentials return 401 Unauthorized
- [ ] Response includes accessToken and refreshToken
- [ ] User info returned (id, email, role, name)
- [ ] Tests cover: valid login, invalid password, user not found

**Learning Topics:**

- Login flow
- Password comparison
- Token generation

---

#### **2.3: Refresh Token Mechanism**

**Goal:** Token refresh without re-login

**Approval Criteria:**

- [ ] POST /auth/refresh endpoint created
- [ ] Accepts refreshToken in request body
- [ ] Returns new accessToken
- [ ] Refresh token validated before returning new token
- [ ] Old token can still be used temporarily
- [ ] Token expiry times: access=1hr, refresh=7days
- [ ] Tests cover: valid refresh, invalid refresh, expired refresh

**Learning Topics:**

- Refresh token pattern
- Token expiry strategies
- Token rotation

---

#### **2.4: Logout Implementation**

**Goal:** Token blacklisting preparation

**Approval Criteria:**

- [ ] POST /auth/logout endpoint created
- [ ] Logout stores token in blacklist (Redis or DB)
- [ ] Blacklisted tokens rejected on future requests
- [ ] Tests cover: logout success, token rejected after logout

**Learning Topics:**

- Token blacklisting
- Token lifecycle management

---

#### **2.5: Google OAuth Setup**

**Goal:** Third-party authentication with Google

**Approval Criteria:**

- [ ] Google OAuth credentials configured
- [ ] GET /auth/google redirects to Google login
- [ ] GET /auth/google/callback handles Google response
- [ ] State parameter validates CSRF protection
- [ ] User created from OAuth profile
- [ ] Existing user linked if email matches
- [ ] JWT tokens returned after OAuth
- [ ] Tests cover: valid OAuth flow, state validation, user linking

**Learning Topics:**

- OAuth 2.0 authorization code flow
- Third-party authentication
- CSRF protection

---

#### **2.6: Role-Based Access Control (RBAC)**

**Goal:** Authorization middleware and permission system

**Approval Criteria:**

- [ ] Roles defined: admin, organizer, member
- [ ] Permission matrix created
- [ ] Authorization middleware implemented
- [ ] Route protection: only authorized roles can access
- [ ] Admin endpoints restricted (GET /users, DELETE /users/:id)
- [ ] Organizer endpoints restricted (create groups, sessions)
- [ ] 401 returned for unauthenticated requests
- [ ] 403 returned for unauthorized requests
- [ ] Tests cover: all 3 roles, all permission scenarios

**Learning Topics:**

- RBAC design patterns
- Authorization middleware
- Permission matrices

---

#### **2.7: User Profile Endpoints**

**Goal:** User management and profile viewing

**Approval Criteria:**

- [ ] GET /users/me returns current authenticated user
- [ ] GET /users/:id returns public user profile
- [ ] PUT /users/:id allows editing own profile
- [ ] User can change: name, avatar, bio
- [ ] User cannot change: email, password, role (via profile)
- [ ] Only owner or admin can edit profile
- [ ] Passwords never returned in API responses
- [ ] Tests cover: view profile, edit own, cannot edit others

**Learning Topics:**

- RESTful API design
- Data ownership validation
- Response formatting

---

#### **2.8: Admin User Management**

**Goal:** Admin endpoints for user management

**Approval Criteria:**

- [ ] GET /users lists all users (admin only)
- [ ] Pagination works: page, limit, total
- [ ] Search/filter by email or name (optional)
- [ ] DELETE /users/:id removes user (admin only)
- [ ] Cascade: deleting user removes their data
- [ ] Tests cover: list users, delete user, non-admin blocked

**Learning Topics:**

- Admin operations
- Cascade deletion
- Pagination

---

#### **2.9: Password Change & Reset**

**Goal:** Secure password management

**Approval Criteria:**

- [ ] POST /auth/change-password requires current password
- [ ] New password validated (strength rules)
- [ ] Old and new password different
- [ ] POST /auth/forgot-password sends reset email (setup, not send)
- [ ] Reset token created with expiry (1 hour)
- [ ] Reset link contains secure token
- [ ] Tests cover: valid change, wrong current pwd, weak new pwd

**Learning Topics:**

- Password change flow
- Reset token generation
- Email token patterns

---

#### **2.10: Input Validation Framework**

**Goal:** Consistent validation across auth endpoints

**Approval Criteria:**

- [ ] Joi or Zod schemas created for each endpoint
- [ ] Email format validated
- [ ] Password format validated
- [ ] Required fields checked
- [ ] Invalid input returns 400 with error details
- [ ] Validation runs before business logic
- [ ] Error messages helpful and non-leaking
- [ ] Tests cover: invalid email, short password, missing fields

**Learning Topics:**

- Input validation libraries
- Schema validation
- Error messages

---

### **Phase 2 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met

---

---

## **PHASE 3: Study Groups & Sessions + Read Caching (Week 5-6)**

**Goals:**

- Complete group management system
- Session scheduling and attendance
- Topic organization
- Redis read caching (cache-aside pattern)
- Understand caching benefits

### **Tasks**

#### **3.1: Create Study Group**

**Goal:** Group creation and management

**Approval Criteria:**

- [ ] POST /groups creates new group
- [ ] Required: name, description
- [ ] Only authenticated users can create (role: organizer)
- [ ] Group creator becomes organizer
- [ ] Response includes group id, creator info
- [ ] Tests cover: create with valid data, unauthorized, missing fields

**Learning Topics:**

- One-to-many relationships
- API creation patterns

---

#### **3.2: List User Groups**

**Goal:** User can see all groups they belong to

**Approval Criteria:**

- [ ] GET /groups lists user's groups
- [ ] Only shows groups user is member of
- [ ] Pagination: page, limit, total
- [ ] Results include member count
- [ ] Sorting by: created date, name
- [ ] Tests cover: list groups, pagination, non-members excluded

**Learning Topics:**

- Many-to-many relationships
- Pagination patterns

---

#### **3.3: Get Group Details**

**Goal:** View full group information

**Approval Criteria:**

- [ ] GET /groups/:id returns group details
- [ ] Includes: members list, session count, topic count
- [ ] Only members can view
- [ ] Non-members get 403
- [ ] **Cache this endpoint** (Redis, TTL: 10 min)
- [ ] Cache invalidates when group updated
- [ ] Tests cover: member access, non-member blocked, cache hit

**Learning Topics:**

- Cache-aside pattern
- Cache invalidation

---

#### **3.4: Update Group**

**Goal:** Edit group information

**Approval Criteria:**

- [ ] PUT /groups/:id edits group
- [ ] Only organizer can edit
- [ ] Can change: name, description
- [ ] Cannot change: creator, id
- [ ] Invalidates cache after update
- [ ] Returns updated group
- [ ] Tests cover: organizer edit, non-organizer blocked

**Learning Topics:**

- Update operations
- Cache invalidation

---

#### **3.5: Delete Group**

**Goal:** Remove group and cascade deletes

**Approval Criteria:**

- [ ] DELETE /groups/:id removes group
- [ ] Only organizer can delete
- [ ] Cascade: delete sessions, notes, topics
- [ ] Invalidates all related caches
- [ ] Returns success message
- [ ] Tests cover: organizer delete, non-organizer blocked, cascade

**Learning Topics:**

- Soft vs hard deletes
- Cascade operations

---

#### **3.6: Group Members Management**

**Goal:** Add and remove group members

**Approval Criteria:**

- [ ] POST /groups/:id/members adds member
- [ ] Only organizer can add
- [ ] User cannot be added twice
- [ ] DELETE /groups/:id/members/:userId removes member
- [ ] GET /groups/:id/members lists members
- [ ] Lists include: name, email, role in group, joined date
- [ ] Tests cover: add member, duplicate rejection, remove member

**Learning Topics:**

- Junction table management
- Member operations

---

#### **3.7: Create Session**

**Goal:** Schedule study sessions

**Approval Criteria:**

- [ ] POST /groups/:id/sessions creates session
- [ ] Required: title, topic_id, scheduled_at, duration_minutes
- [ ] Only organizer can create
- [ ] Cannot create session with past date
- [ ] Session capacity validated (> 0)
- [ ] Returns session object with id
- [ ] Tests cover: valid session, past date rejected, invalid capacity

**Learning Topics:**

- DateTime validation
- Timezone handling

---

#### **3.8: List & Filter Sessions**

**Goal:** View group sessions with filtering

**Approval Criteria:**

- [ ] GET /groups/:id/sessions lists sessions
- [ ] Filter by: topic_id, status (scheduled/ongoing/completed)
- [ ] Pagination: page, limit, total
- [ ] **Cache this endpoint** (TTL: 5 min)
- [ ] Sorted by scheduled_at (default: ascending)
- [ ] Tests cover: list, filtering, pagination, cache

**Learning Topics:**

- Query filtering
- Multiple filter combinations

---

#### **3.9: Session Details & Attendance**

**Goal:** View session with attendees

**Approval Criteria:**

- [ ] GET /sessions/:id returns session details
- [ ] Includes: attendees list with status
- [ ] Only members can view
- [ ] **Cache this endpoint** (TTL: 5 min)
- [ ] Attendee count displayed
- [ ] Tests cover: member access, attendee info, cache

**Learning Topics:**

- Relationship querying

---

#### **3.10: Attendance Management**

**Goal:** Users attend/cancel sessions

**Approval Criteria:**

- [ ] POST /sessions/:id/attend marks user attending
- [ ] Cannot attend past sessions
- [ ] Cannot exceed capacity
- [ ] Returns attendance confirmation
- [ ] DELETE /sessions/:id/attend cancels attendance
- [ ] Cannot cancel if session completed
- [ ] Invalidates session cache
- [ ] Tests cover: attend, exceed capacity, past session, cancel

**Learning Topics:**

- Transaction management
- Business logic validation

---

#### **3.11: Topic Management**

**Goal:** Organize topics within groups

**Approval Criteria:**

- [ ] POST /groups/:id/topics creates topic
- [ ] Required: name, description
- [ ] GET /groups/:id/topics lists topics with pagination
- [ ] Status field: todo, in_progress, completed
- [ ] PUT /topics/:id updates topic
- [ ] Invalidates cache when updated
- [ ] Tests cover: create, list, update, soft delete

**Learning Topics:**

- Status transitions
- Soft deletes

---

### **Phase 3 Completion Criteria**

**Phase Complete When:** ALL 11+ tasks have approval criteria met

---

---

## **PHASE 4: Notes & Cache Invalidation (Week 7-8)**

**Goals:**

- Notes CRUD system
- Tags and search
- Smart cache invalidation (critical learning)
- Understand cache complexity

### **Tasks**

#### **4.1: Create Notes**

**Goal:** Users add notes to group or session

**Approval Criteria:**

- [ ] POST /groups/:id/notes creates note
- [ ] Required: title, content (Markdown)
- [ ] Optional: topic_id, session_id, tags
- [ ] Any group member can create
- [ ] Content length: 1-10,000 characters
- [ ] Invalidates group notes cache
- [ ] Returns note object with id
- [ ] Tests cover: create, content validation, cache invalidation

**Learning Topics:**

- Content validation
- Markdown handling

---

#### **4.2: List & Search Notes**

**Goal:** Find notes with filtering and search

**Approval Criteria:**

- [ ] GET /groups/:id/notes lists notes with pagination
- [ ] GET /groups/:id/notes/search with query parameter
- [ ] Search in: title, content (case-insensitive)
- [ ] Filter by: topic_id, tag, created_by, session_id
- [ ] **Cache list endpoint** (TTL: 5 min)
- [ ] Search results not cached (freshness critical)
- [ ] Performance: search 1000 notes < 500ms
- [ ] Tests cover: list, search, filters, pagination, performance

**Learning Topics:**

- PostgreSQL LIKE search
- Query performance
- Search optimization

---

#### **4.3: Get Note Details**

**Goal:** View full note content

**Approval Criteria:**

- [ ] GET /notes/:id returns note details
- [ ] Only group members can view
- [ ] Includes: title, content, creator, created_at, updated_at
- [ ] **Cache this endpoint** (TTL: 5 min)
- [ ] Tests cover: member access, non-member blocked, cache

**Learning Topics:**

- Relationship queries

---

#### **4.4: Update Notes**

**Goal:** Edit note content

**Approval Criteria:**

- [ ] PUT /notes/:id edits note
- [ ] Only creator can edit
- [ ] Can change: title, content, topic_id, tags
- [ ] Updates updated_at and updated_by
- [ ] **Invalidates ALL related caches** (critical!)
- [ ] Returns updated note
- [ ] Tests cover: creator edit, non-creator blocked, cache invalidation

**Learning Topics:**

- Cache invalidation patterns
- Cascade invalidation

---

#### **4.5: Delete Notes**

**Goal:** Remove notes from group

**Approval Criteria:**

- [ ] DELETE /notes/:id removes note
- [ ] Only creator can delete
- [ ] **Invalidates note cache and group notes cache**
- [ ] Tests cover: creator delete, non-creator blocked, cache invalidation

**Learning Topics:**

- Cascade invalidation

---

#### **4.6: Tags Creation**

**Goal:** Organize notes with tags

**Approval Criteria:**

- [ ] POST /groups/:id/tags creates tag
- [ ] Required: name (unique within group)
- [ ] Tags are group-specific
- [ ] GET /groups/:id/tags lists all tags
- [ ] Tests cover: create, duplicate rejection, list

**Learning Topics:**

- Many-to-many relationships (note_tags)

---

#### **4.7: Note Tagging**

**Goal:** Associate tags with notes

**Approval Criteria:**

- [ ] POST /notes/:id/tags/:tagId adds tag to note
- [ ] DELETE /notes/:id/tags/:tagId removes tag
- [ ] One note can have multiple tags
- [ ] Invalidates note cache when tags change
- [ ] Tests cover: add tag, remove tag, multiple tags

**Learning Topics:**

- Junction table operations

---

#### **4.8: Filter by Tags**

**Goal:** Find notes by tags

**Approval Criteria:**

- [ ] GET /notes?tags=tag1,tag2 filters notes
- [ ] Notes with ANY of specified tags returned
- [ ] Results paginated
- [ ] Performance acceptable (< 500ms)
- [ ] Tests cover: single tag, multiple tags, pagination

**Learning Topics:**

- Complex filtering

---

#### **4.9: Markdown Content Security**

**Goal:** Prevent XSS and sanitize content

**Approval Criteria:**

- [ ] Markdown content stored as-is
- [ ] HTML rendering sanitizes: no scripts, no dangerous tags
- [ ] Links safe (no javascript: protocol)
- [ ] Images whitelisted or disabled
- [ ] Tests cover: script injection attempts, safe rendering

**Learning Topics:**

- XSS prevention
- HTML sanitization
- Markdown libraries

---

#### **4.10: Cache Invalidation Strategy**

**Goal:** Prevent stale data in cache (critical learning)

**Approval Criteria:**

- [ ] When note created: invalidate group notes cache
- [ ] When note updated: invalidate note cache + group notes cache
- [ ] When note deleted: invalidate note cache + group notes cache
- [ ] When tag added: invalidate note cache + tag filter cache
- [ ] Cascade invalidation: delete group → delete all related caches
- [ ] **Tests verify: NO STALE DATA returned from cache**
- [ ] Cache hit rate logged for monitoring
- [ ] Tests cover: all invalidation scenarios, stale data detection

**Learning Topics:**

- Cache invalidation patterns
- Eventual consistency
- Cache monitoring

---

### **Phase 4 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met  
**CRITICAL:** Zero stale data bugs - cache invalidation is correct

---

---

## **PHASE 5: Real-Time Features & Kafka Events (Week 9-10)**

**Goals:**

- WebSocket real-time updates
- User presence tracking
- Event streaming with Kafka
- Background job processing

### **Tasks**

#### **5.1: WebSocket Setup & Authentication**

**Goal:** Real-time bidirectional communication

**Approval Criteria:**

- [ ] Socket.io integrated with Express
- [ ] Socket authentication middleware verifies JWT
- [ ] Invalid tokens reject connection
- [ ] User data attached to socket
- [ ] Connection/disconnect events logged
- [ ] Tests cover: valid token, invalid token, disconnect handling

**Learning Topics:**

- WebSocket protocol
- Socket.io architecture

---

#### **5.2: Room Management**

**Goal:** Organize socket connections by scope

**Approval Criteria:**

- [ ] User rooms: user:{userId}
- [ ] Group rooms: group:{groupId}
- [ ] Session rooms: session:{sessionId}
- [ ] Users automatically join relevant rooms on connect
- [ ] Users leave rooms on disconnect
- [ ] Broadcasting to rooms works
- [ ] Tests cover: room joining, broadcasting, leave

**Learning Topics:**

- Socket.io rooms
- Broadcasting patterns

---

#### **5.3: User Status Updates**

**Goal:** Real-time presence tracking

**Approval Criteria:**

- [ ] Socket event: user:status with status (online/offline/studying)
- [ ] Status broadcast to user's groups
- [ ] Last activity timestamp updated
- [ ] All group members see status changes in real-time
- [ ] Offline detection on disconnect
- [ ] Tests cover: status change, broadcast, offline detection

**Learning Topics:**

- Presence patterns
- Real-time broadcast

---

#### **5.4: Session Real-Time Updates**

**Goal:** Live session synchronization

**Approval Criteria:**

- [ ] Session updates broadcast to attendees
- [ ] Attendee joins broadcast to session room
- [ ] Attendee leaves broadcast to session room
- [ ] Real-time attendee count
- [ ] Session start/end events broadcast
- [ ] Tests cover: updates, joins, leaves, count accuracy

**Learning Topics:**

- Event broadcasting

---

#### **5.5: Kafka Setup in Docker**

**Goal:** Event streaming infrastructure

**Approval Criteria:**

- [ ] Kafka broker running in docker-compose
- [ ] Zookeeper configured
- [ ] Kafka topics created: sessions.created, notes.created, users.online
- [ ] Topics accessible from app
- [ ] Tests cover: topic creation, producer sends to topic

**Learning Topics:**

- Kafka concepts
- Topic and partition design

---

#### **5.6: Event Producer**

**Goal:** Publish events to Kafka topics

**Approval Criteria:**

- [ ] Kafka producer initialized
- [ ] Events published on: session create, note create, user online
- [ ] Event format consistent (JSON with metadata)
- [ ] Error handling if producer fails (log, don't crash)
- [ ] Tests cover: event publishing, format, error handling

**Learning Topics:**

- Producer-consumer pattern
- Event serialization

---

#### **5.7: Event Consumer - Notifications**

**Goal:** Process events for notifications

**Approval Criteria:**

- [ ] Kafka consumer subscribed to: sessions.created, notes.created
- [ ] Consumer processes events asynchronously
- [ ] Notifications created in database
- [ ] Notifications emitted to users via Socket.io
- [ ] Error handling: failed events logged, not lost
- [ ] Tests cover: event processing, notification creation

**Learning Topics:**

- Consumer groups
- Event processing

---

#### **5.8: Event Consumer - Session Reminders**

**Goal:** Background job for session reminders

**Approval Criteria:**

- [ ] Consumer subscribed to: sessions.created
- [ ] Reminder scheduled for 1 hour before session
- [ ] Reminder emitted to attendees via Socket.io
- [ ] Timezone aware (use user timezone if available)
- [ ] Tests cover: reminder scheduling, proper timing

**Learning Topics:**

- Scheduling patterns
- Background jobs

---

#### **5.9: Event Consumer - Analytics**

**Goal:** Aggregate analytics from events

**Approval Criteria:**

- [ ] Consumer subscribed to: sessions.completed, notes.created
- [ ] Analytics collected: attendance rate, notes per user, active hours
- [ ] Analytics stored in cache or analytics table
- [ ] Events processed without duplicates
- [ ] Tests cover: event aggregation, analytics accuracy

**Learning Topics:**

- Analytics processing
- Idempotency

---

#### **5.10: Real-Time Notification System**

**Goal:** In-app notifications from Socket.io

**Approval Criteria:**

- [ ] GET /notifications returns user's notifications
- [ ] Unread count accurate
- [ ] PUT /notifications/:id/read marks as read
- [ ] Socket event: notification:new broadcasts to user
- [ ] Notification badge updates in real-time
- [ ] Tests cover: get, mark-read, real-time emission

**Learning Topics:**

- Notification patterns

---

#### **5.11: Error Handling & Graceful Degradation**

**Goal:** System reliability with real-time features

**Approval Criteria:**

- [ ] Socket disconnects handled gracefully
- [ ] Reconnection restores state
- [ ] WebSocket failures don't crash server
- [ ] Kafka consumer failures logged and retried
- [ ] Tests cover: disconnect/reconnect, consumer failure, recovery

**Learning Topics:**

- Error handling
- Fault tolerance

---

### **Phase 5 Completion Criteria**

**Phase Complete When:** ALL 11+ tasks have approval criteria met

---

---

## **PHASE 6: Progress Tracking & Worker Services (Week 11-12)**

**Goals:**

- User and group progress tracking
- Kafka-based worker services
- Analytics aggregation
- Data consistency

### **Tasks**

#### **6.1: Progress Tracking Model**

**Goal:** Track topic completion per user

**Approval Criteria:**

- [ ] user_progress table created
- [ ] Fields: user_id, topic_id, status, started_at
- [ ] Status values: todo, in_progress, completed
- [ ] Timestamps tracked (started_at, completed_at)
- [ ] Unique constraint: one record per user-topic pair

**Learning Topics:**

- Data modeling for tracking

---

#### **6.2: Update Progress Endpoint**

**Goal:** Users mark topic progress

**Approval Criteria:**

- [ ] POST /users/progress/:topicId marks status
- [ ] Status values: todo, in_progress, completed
- [ ] Only authenticated users can update own progress
- [ ] Returns updated progress object
- [ ] Tests cover: valid status, invalid status, ownership

**Learning Topics:**

- State transitions

---

#### **6.3: User Progress Dashboard**

**Goal:** View individual progress

**Approval Criteria:**

- [ ] GET /users/:id/progress returns user's progress
- [ ] Shows: all topics, current status, started_at, completed_at
- [ ] Completion percentage calculated
- [ ] Tests cover: progress retrieval, percentage accuracy

**Learning Topics:**

- Aggregation queries

---

#### **6.4: Group Progress Dashboard**

**Goal:** View group-level progress

**Approval Criteria:**

- [ ] GET /groups/:id/progress returns group progress
- [ ] Shows: topics, % complete, members per topic
- [ ] Completion % by topic (how many members completed)
- [ ] Member status per topic
- [ ] Tests cover: group progress, accuracy, aggregation

**Learning Topics:**

- Complex aggregations

---

#### **6.5: Milestones & Deadlines**

**Goal:** Track group milestones

**Approval Criteria:**

- [ ] POST /groups/:id/milestones creates milestone
- [ ] Milestone has: name, deadline, topics included
- [ ] GET /milestones shows progress toward milestone
- [ ] Tests cover: create, retrieve, progress tracking

**Learning Topics:**

- Milestone management

---

#### **6.6: Attendance Analytics Worker**

**Goal:** Aggregate attendance statistics

**Approval Criteria:**

- [ ] Worker consumes: session.completed events
- [ ] Calculates: attendance rate per user, per group
- [ ] Stores: user stats (attended, total, rate%)
- [ ] Stats updated in cache for fast retrieval
- [ ] Tests cover: calculation accuracy, stats retrieval

**Learning Topics:**

- Statistics aggregation

---

#### **6.7: User Activity Analytics Worker**

**Goal:** Track user engagement

**Approval Criteria:**

- [ ] Worker consumes: notes.created, users.online events
- [ ] Tracks: notes created per user, active days
- [ ] Stores: weekly active users, monthly active users
- [ ] Tests cover: tracking accuracy, edge cases

**Learning Topics:**

- Engagement metrics

---

#### **6.8: Worker Error Handling & Retry**

**Goal:** Reliable background processing

**Approval Criteria:**

- [ ] Failed events logged with context
- [ ] Retry mechanism for transient failures
- [ ] Dead letter queue for persistent failures
- [ ] Worker health monitoring
- [ ] Tests cover: failure handling, recovery, DLQ

**Learning Topics:**

- Reliability patterns
- Dead letter queues

---

#### **6.9: Data Validation & Consistency**

**Goal:** Ensure data integrity across async operations

**Approval Criteria:**

- [ ] All operations validated before processing
- [ ] Concurrent updates handled (transactions)
- [ ] Business rules enforced (can't complete topic with unattended sessions)
- [ ] Cascade operations consistent
- [ ] Tests cover: edge cases, concurrent scenarios

**Learning Topics:**

- Transaction management
- Consistency patterns

---

#### **6.10: Notification Worker**

**Goal:** Process and send notifications

**Approval Criteria:**

- [ ] Worker consumes: notifications.needed events
- [ ] Creates notification record in database
- [ ] Emits via Socket.io to user
- [ ] Marks delivered when user receives
- [ ] Tests cover: notification creation, delivery

**Learning Topics:**

- Notification processing

---

### **Phase 6 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met

---

---

## **PHASE 7: AWS Deployment & CI/CD Integration (Week 13-14)**

**Goals:**

- Deploy to AWS EC2
- Production-ready infrastructure
- Automated deployment pipeline
- Monitoring and logging

### **Tasks**

#### **7.1: AWS Account & Security Setup**

**Goal:** Secure AWS foundation

**Approval Criteria:**

- [ ] AWS account created with appropriate IAM roles
- [ ] Access keys configured for CI/CD
- [ ] Security groups defined
- [ ] VPC configured (if needed)
- [ ] Secrets managed in AWS Secrets Manager

**Learning Topics:**

- AWS IAM
- Security best practices

---

#### **7.2: EC2 Instance Setup**

**Goal:** Application server in cloud

**Approval Criteria:**

- [ ] EC2 instance created and running
- [ ] Correct instance type chosen
- [ ] SSH key pair created and secured
- [ ] Instance accessible via SSH
- [ ] Docker installed on instance
- [ ] Docker Compose installed

**Learning Topics:**

- EC2 fundamentals
- SSH access

---

#### **7.3: RDS PostgreSQL Database**

**Goal:** Managed database in cloud

**Approval Criteria:**

- [ ] RDS PostgreSQL instance created
- [ ] Accessible from EC2 instance
- [ ] Backups configured
- [ ] Security group allows EC2 connection
- [ ] Database created and migrations run
- [ ] Connection pooling configured

**Learning Topics:**

- RDS setup
- Database connectivity

---

#### **7.4: ElastiCache Redis**

**Goal:** Managed Redis in cloud

**Approval Criteria:**

- [ ] ElastiCache Redis cluster created
- [ ] Accessible from EC2 instance
- [ ] Security group configured
- [ ] Connection string in environment variables
- [ ] Persistence enabled (optional)

**Learning Topics:**

- ElastiCache setup
- Redis clustering

---

#### **7.5: Application Deployment**

**Goal:** Deploy app to EC2

**Approval Criteria:**

- [ ] Git repository cloned on EC2
- [ ] Environment variables configured
- [ ] Docker image built on instance (or pulled from registry)
- [ ] Container started with systemd or docker-compose
- [ ] Health check endpoint accessible
- [ ] Logs accessible and searchable

**Learning Topics:**

- Application deployment
- Container orchestration

---

#### **7.6: CI/CD Pipeline to AWS**

**Goal:** Automated deployment on GitHub merge

**Approval Criteria:**

- [ ] GitHub Actions deploys to EC2 on main branch push
- [ ] Deployment steps: pull code, run migrations, build, restart
- [ ] Rollback procedure documented
- [ ] Pre-deployment smoke tests run
- [ ] Deployment logs stored
- [ ] Tests cover: deployment success, rollback

**Learning Topics:**

- Deployment automation
- CI/CD integration

---

#### **7.7: Database Migrations in Production**

**Goal:** Safe database schema changes

**Approval Criteria:**

- [ ] Migrations run automatically before app starts
- [ ] Rollback procedure for failed migrations
- [ ] Data backup before migrations
- [ ] Zero-downtime migration strategy (if possible)
- [ ] Tests cover: migration success, rollback

**Learning Topics:**

- Production migrations
- Zero-downtime deploys

---

#### **7.8: Kafka on EC2 or Managed Service**

**Goal:** Event streaming in production

**Approval Criteria:**

- [ ] Kafka broker deployed (EC2 or AWS MSK)
- [ ] Topics created
- [ ] Consumers connect successfully
- [ ] Replication configured
- [ ] Monitoring enabled

**Learning Topics:**

- Production Kafka setup

---

#### **7.9: CloudWatch Logging**

**Goal:** Centralized logging and monitoring

**Approval Criteria:**

- [ ] Application logs sent to CloudWatch
- [ ] Log groups and streams organized
- [ ] JSON structured logs
- [ ] Error alerts configured
- [ ] Log retention policy set

**Learning Topics:**

- CloudWatch logging
- Log aggregation

---

#### **7.10: Environment Configuration Management**

**Goal:** Secure secrets and config in production

**Approval Criteria:**

- [ ] Secrets stored in AWS Secrets Manager
- [ ] No secrets in code or config files
- [ ] Environment variables loaded from Secrets Manager
- [ ] Rotation policy for sensitive secrets
- [ ] Tests cover: secrets loading, no leaks

**Learning Topics:**

- Secrets management
- Configuration management

---

### **Phase 7 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met

---

---

## **PHASE 8: Optimization, Security & Documentation (Week 15-16)**

**Goals:**

- Performance optimization
- Security hardening
- Complete documentation
- Production readiness

### **Tasks**

#### **8.1: Database Query Optimization**

**Goal:** Fast queries and efficient indexing

**Approval Criteria:**

- [ ] Indexes created on frequently queried columns
- [ ] Query performance profiled (EXPLAIN ANALYZE)
- [ ] N+1 queries eliminated
- [ ] JOIN queries optimized
- [ ] Slow query log reviewed and tuned
- [ ] Tests cover: query performance targets

**Learning Topics:**

- Query optimization
- Index strategies

---

#### **8.2: Connection Pooling Tuning**

**Goal:** Efficient database connections

**Approval Criteria:**

- [ ] Connection pool size optimized
- [ ] Pool timeout configured
- [ ] Connection reuse validated
- [ ] No connection leaks
- [ ] Load testing validates pooling

**Learning Topics:**

- Connection pooling

---

#### **8.3: Redis Cache Optimization**

**Goal:** Maximize cache effectiveness

**Approval Criteria:**

- [ ] Cache hit rates monitored and > 80%
- [ ] TTL values optimized for each endpoint
- [ ] Memory usage acceptable
- [ ] No over-caching (stale data risk)
- [ ] Tests cover: hit rates, memory usage

**Learning Topics:**

- Cache strategies
- Monitoring metrics

---

#### **8.4: Load Testing & Performance Targets**

**Goal:** Validate performance under load

**Approval Criteria:**

- [ ] Load test with 100 concurrent users
- [ ] Response time: p95 < 500ms, p99 < 1000ms
- [ ] No errors under load
- [ ] Database connections stable
- [ ] Redis hit rates maintained
- [ ] Tests generate load test results

**Learning Topics:**

- Load testing tools
- Performance profiling

---

#### **8.5: Security Audit - OWASP Top 10**

**Goal:** Harden against common vulnerabilities

**Approval Criteria:**

- [ ] SQL injection prevention verified
- [ ] XSS protection tested
- [ ] CSRF protection (state parameter, SameSite cookies)
- [ ] CORS properly configured (not overly permissive)
- [ ] Authentication/Authorization: role checks working
- [ ] Sensitive data: no passwords in logs, no data leaks
- [ ] HTTPS enforced in production
- [ ] Security headers configured (HSTS, CSP, etc.)

**Learning Topics:**

- OWASP security
- Security hardening

---

#### **8.6: Input Validation Comprehensive Review**

**Goal:** Prevent malicious input processing

**Approval Criteria:**

- [ ] All endpoints validate input
- [ ] Edge cases handled (null, empty, very long strings)
- [ ] Type checking enforced
- [ ] Business rule validation
- [ ] Error messages non-revealing
- [ ] Tests cover: invalid input, edge cases, injection attempts

**Learning Topics:**

- Input validation
- Security testing

---

#### **8.7: API Documentation Complete**

**Goal:** Comprehensive API documentation

**Approval Criteria:**

- [ ] All endpoints documented (path, method, params, response)
- [ ] Authentication requirements clear
- [ ] Error codes documented
- [ ] Examples provided
- [ ] TypeScript interfaces documented
- [ ] Format: OpenAPI/Swagger or Markdown
- [ ] Accessible and searchable

**Learning Topics:**

- API documentation
- OpenAPI spec

---

#### **8.8: Code Quality & Linting**

**Goal:** Clean, consistent codebase

**Approval Criteria:**

- [ ] ESLint passes with no warnings
- [ ] Prettier formatting consistent
- [ ] TypeScript strict compilation
- [ ] No unused variables or imports
- [ ] Meaningful variable/function names
- [ ] Code comments for complex logic
- [ ] No console.log (use logger)

**Learning Topics:**

- Code quality tools
- Linting

---

#### **8.9: Test Coverage Target Achievement**

**Goal:** Comprehensive test coverage

**Approval Criteria:**

- [ ] Coverage >= 70% for critical paths
- [ ] Unit tests for business logic
- [ ] Integration tests for API endpoints
- [ ] Database transaction tests
- [ ] Error scenario tests
- [ ] Cache invalidation tests (critical!)
- [ ] No test flakiness

**Learning Topics:**

- Test coverage metrics
- Testing strategies

---

#### **8.10: Final Documentation & README**

**Goal:** Complete project documentation

**Approval Criteria:**

- [ ] README.md: setup instructions, running locally, testing
- [ ] AGENTS.md: guidelines for AI assistance (created together)
- [ ] RULES.md: development conventions (created together)
- [ ] ARCHITECTURE.md: design decisions, tech choices
- [ ] DEPLOYMENT.md: production deployment instructions
- [ ] LEARNING_RESOURCES.md: references and links
- [ ] CONTRIBUTION.md: how to contribute (optional)

**Learning Topics:**

- Documentation best practices

---

### **Phase 8 Completion Criteria**

**Phase Complete When:** ALL 10+ tasks have approval criteria met

---

---

## **Success Metrics**

**Project Completion:**

- [ ] All 8 phases complete (80+ tasks)
- [ ] Test coverage >= 70%
- [ ] Zero critical security vulnerabilities
- [ ] Performance: p95 response time < 500ms (100 concurrent users)
- [ ] All approval criteria met
- [ ] Documentation complete
- [ ] Deployed and running on AWS

**Learning Outcomes:**

- Full-stack backend architecture understanding
- Database design and optimization
- API design and security
- Real-time system design (WebSockets)
- Event-driven architecture (Kafka)
- Cloud deployment (AWS)
- Production operations

---

## **Key Resources (via Context7)**

**TypeScript:**

- /microsoft/typescript (High reputation, 18,942 snippets)
- /websites/typescriptlang (High reputation, 91.3 benchmark score)
- /websites/ts_dev-style (Style guide, High reputation)

**Node.js:**

- /nodejs/node (Official, High reputation, 8,263 snippets)
- /websites/nodejs_api (Official API docs, 80.8 benchmark score)
- /goldbergyoni/nodebestpractices (Best practices collection, High reputation)

**Continue with Context7 lookups as needed for specific topics**

---

**Roadmap Status:** Ready for implementation  
**Next Step:** Create AGENTS.md and RULES.md together with user

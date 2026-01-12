# RULES.md

**Development Rules & Conventions**

---

## **📌 Code Style & Formatting**

### **TypeScript Rules**
- ✅ Strict mode: `strict: true` in tsconfig.json
- ✅ No `any` type - always be explicit
- ✅ All functions have explicit return types
- ✅ All interfaces/types exported from types/ folder
- ✅ Use `interface` for object contracts, `type` for unions/primitives
- ✅ Enums for constants (not string literals)

### **Naming Conventions**
```typescript
// Classes & Interfaces: PascalCase
class UserRepository { }
interface UserDTO { }

// Functions & variables: camelCase
function getUserById() { }
const maxRetries = 3;

// Constants: UPPER_SNAKE_CASE
const MAX_CONNECTIONS = 100;
const API_TIMEOUT_MS = 5000;

// Database fields: snake_case
const created_at: Date;
const user_id: string;

// API paths: kebab-case
/api/study-groups/:id/sessions
```

### **File Naming**
```
src/
├── features/auth/
│   ├── auth.service.ts        (service)
│   ├── auth.controller.ts      (controller)
│   ├── auth.routes.ts          (routes)
│   ├── auth.types.ts           (types)
│   └── auth.test.ts            (tests)
```

---

## **🧪 Testing Rules**

### **TDD Approach**
1. Write test first (RED)
2. Write code to pass test (GREEN)
3. Refactor if needed (REFACTOR)

### **Test File Location**
```
Feature code:    src/features/feature-name/feature.service.ts
Test code:       src/features/feature-name/feature.test.ts
                 OR tests/feature-name.test.ts
```

### **Test Naming**
```typescript
describe('UserService', () => {
  describe('create', () => {
    test('should create user with valid data', () => { });
    test('should reject duplicate email', () => { });
    test('should hash password', () => { });
  });
});
```

### **Test Coverage Goals**
- Unit tests: Business logic (services)
- Integration tests: API endpoints (controllers + routes)
- Database tests: Queries and relationships
- Cache tests: Hit/miss, invalidation
- Target: 70%+ coverage for critical paths

### **Test Database**
- Separate from development database
- Clean state before each test
- Use test fixtures for consistent data
- Rollback or clear after each test

---

## **📁 Folder Organization**

```
study-group-backend/
├── src/
│   ├── features/                      # Feature-based organization
│   │   ├── auth/
│   │   │   ├── routes/auth.routes.ts
│   │   │   ├── controllers/auth.controller.ts
│   │   │   ├── services/auth.service.ts
│   │   │   ├── models/User.ts
│   │   │   ├── middleware/auth.middleware.ts
│   │   │   ├── types/auth.types.ts
│   │   │   └── auth.test.ts
│   │   │
│   │   ├── groups/
│   │   ├── sessions/
│   │   ├── notes/
│   │   ├── notifications/
│   │   ├── topics/
│   │   └── users/
│   │
│   ├── shared/                        # Cross-cutting concerns
│   │   ├── middleware/
│   │   │   ├── errorHandler.ts
│   │   │   ├── requestLogger.ts
│   │   │   └── validate.ts
│   │   ├── utils/
│   │   │   ├── jwt.ts
│   │   │   ├── passwordHash.ts
│   │   │   ├── logger.ts
│   │   │   ├── errors.ts
│   │   │   └── constants.ts
│   │   ├── guards/
│   │   │   └── authorization.ts
│   │   ├── database/
│   │   │   ├── connection.ts
│   │   │   ├── migrations/
│   │   │   └── seeders/
│   │   └── socket/
│   │       ├── socketManager.ts
│   │       ├── handlers/
│   │       └── middleware/
│   │
│   ├── config/
│   │   ├── env.ts
│   │   ├── database.ts
│   │   ├── server.ts
│   │   └── constants.ts
│   │
│   ├── app.ts                         # Express app setup
│   ├── server.ts                      # Server startup
│   └── index.ts                       # Entry point
│
├── tests/
│   ├── unit/
│   ├── integration/
│   └── fixtures/
│
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
│
├── roadmap/
│   ├── ROADMAP.md
│   ├── TYPESCRIPT_SETUP.md
│   ├── LEARNING_RESOURCES.md
│   ├── AGENTS.md
│   └── RULES.md
│
├── .github/workflows/
│   └── ci.yml
│
├── tsconfig.json
├── jest.config.js
├── .eslintrc.json
├── .prettierrc
├── docker-compose.yml
├── .env.example
├── .gitignore
├── package.json
└── README.md
```

---

## **💻 Git & Commits**

### **Commit Message Format**
```
feat: add group creation endpoint
fix: cache invalidation on note update
test: add integration tests for auth
docs: update API documentation
refactor: extract validation logic
chore: update dependencies
```

### **Commit Guidelines**
- ✅ Small, focused commits
- ✅ One feature per commit
- ✅ Clear message describing change
- ✅ Include related task/phase number

**Example:**
```
feat(auth): implement email registration
- Add POST /auth/register endpoint
- Password strength validation
- Email uniqueness check
- Tests: 5 test cases

Related: Phase 2, Task 2.1
```

### **Branch Naming**
```
feature/phase-2-authentication
fix/cache-invalidation-bug
docs/api-documentation
```

---

## **🔐 Security Rules**

### **Secrets & Environment Variables**
- ❌ Never commit secrets
- ✅ Use .env for local development
- ✅ Use AWS Secrets Manager for production
- ✅ All secrets loaded at startup
- ✅ Secrets in UPPERCASE

### **Password Handling**
- ✅ Always hash with bcrypt
- ✅ Never store plaintext
- ✅ Min 8 chars, special chars, numbers
- ✅ No password in logs or errors

### **API Security**
- ✅ Validate all inputs
- ✅ Sanitize output
- ✅ CORS configured (not overly permissive)
- ✅ HTTPS in production
- ✅ Rate limiting on auth endpoints

### **Data Protection**
- ✅ No sensitive data in logs
- ✅ No personal data in error messages
- ✅ Database credentials in environment
- ✅ Token secrets 32+ characters

---

## **📝 Comments & Documentation**

### **When to Comment**
✅ **DO comment:**
- Complex algorithms
- Why, not what (code shows what)
- Tricky business logic
- Non-obvious design decisions

❌ **DON'T comment:**
- Obvious code: `const user = await User.find(id)`
- Redundant comments
- Commented-out code (use git history)

### **Comment Style**
```typescript
// Single line comment for short explanations

/**
 * Multi-line comments for complex logic
 * Explain the why and any edge cases
 * @param id - User identifier
 * @returns User object or null if not found
 */
async function getUserById(id: string): Promise<User | null> {
  // Implementation
}
```

### **Code Documentation**
- TypeScript interfaces document parameters
- Return types document output
- Error scenarios documented
- Examples in README

---

## **🔍 Code Review Checklist**

Before committing:
- [ ] Tests pass locally
- [ ] TypeScript compiles with no errors
- [ ] ESLint passes
- [ ] Prettier formatted
- [ ] No console.log (use logger)
- [ ] No dead code
- [ ] Comments explain complex logic
- [ ] Passwords never logged
- [ ] Error messages user-friendly
- [ ] All approval criteria met

---

## **🚀 Deployment Rules**

### **Before Deploying**
- ✅ All tests passing
- ✅ Code quality checks pass
- ✅ Security audit done
- ✅ Documentation updated
- ✅ Database migrations tested
- ✅ Rollback plan ready

### **Deployment Checklist**
- [ ] Pull latest code
- [ ] Run migrations on staging
- [ ] Verify backups
- [ ] Deploy to production
- [ ] Smoke tests pass
- [ ] Monitor logs
- [ ] Communication to users (if needed)

---

## **📊 Logging Rules**

### **Log Levels**
```typescript
logger.debug('Detailed debugging info');
logger.info('General information');
logger.warn('Warning - recoverable issue');
logger.error('Error - something failed');
```

### **Structured Logging**
```typescript
// ✅ Good - structured
logger.info('User login', {
  userId: user.id,
  email: user.email,
  timestamp: new Date(),
  requestId: req.id
});

// ❌ Bad - unstructured
console.log('User logged in: ' + user.email);
```

### **What to Log**
- ✅ Important events (login, session created, etc.)
- ✅ Errors with stack traces
- ✅ Performance issues
- ✅ Security events

### **What NOT to Log**
- ❌ Passwords
- ❌ API keys or tokens
- ❌ Personal data (SSN, etc.)
- ❌ Credit card numbers
- ❌ Every request (too verbose)

---

## **⚡ Performance Rules**

### **Database**
- ✅ Use indexes on frequently queried columns
- ✅ Avoid N+1 queries (eager loading)
- ✅ Use pagination for large results
- ✅ Profile queries: EXPLAIN ANALYZE

### **Caching**
- ✅ Cache read-heavy endpoints
- ✅ Invalidate on writes
- ✅ Set reasonable TTLs
- ✅ Monitor hit rates

### **API Response Times**
- Target: p95 < 500ms, p99 < 1000ms
- Monitor and optimize slow endpoints
- Use load testing to identify bottlenecks

---

## **📚 Documentation Rules**

### **README.md Should Include**
- Project description
- Tech stack
- Setup instructions
- Running locally
- Running tests
- API endpoints (summary)
- Contributing guidelines

### **Task Documentation**
- What was built
- Approval criteria met
- Tests added
- Learning resources used
- Any blockers encountered

### **API Documentation**
- All endpoints listed
- Request/response examples
- Error codes
- Authentication required?
- Rate limits

---

## **🔄 Dependency Management**

### **Adding Dependencies**
- ✅ Ask before adding new packages
- ✅ Prefer popular, well-maintained packages
- ✅ Check for security vulnerabilities
- ✅ Keep versions locked (package-lock.json)

### **Avoiding Dependencies**
- Consider if needed (don't add unnecessary)
- Evaluate license (MIT, Apache preferred)
- Check download count and reputation

---

## **Exceptions & Overrides**

**When can rules be broken?**
- Never: Security rules, data protection
- Rarely: TypeScript strict, testing
- Sometimes: Documentation, comments (if time-limited)

**If bending a rule, document why:**
```typescript
// TODO: Fix TypeScript any type in next iteration
// (used any due to time constraint - Phase 1, Task X)
const data: any = JSON.parse(response);
```

---

## **Questions About These Rules?**

If a rule is:
- **Too restrictive?** Discuss and update it
- **Unclear?** Add an example
- **Conflicting?** Clarify priority

This is a living document. Suggest improvements!

---

**Created:** [Date]  
**Last Updated:** [Date]  
**Version:** 1.0

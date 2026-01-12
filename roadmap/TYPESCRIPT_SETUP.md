# TypeScript Setup Guide

**Goal:** Configure TypeScript with strict mode from the start

---

## **tsconfig.json - Strict Mode Configuration**

```json
{
  "compilerOptions": {
    // Strict Type Checking
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "strictFunctionTypes": true,
    "strictBindCallApply": true,
    "strictPropertyInitialization": true,
    "noImplicitThis": true,
    "useUnknownInCatchVariables": true,

    // Additional Type Checking
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,

    // Module Resolution
    "target": "ES2020",
    "module": "commonjs",
    "lib": ["ES2020"],
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,

    // Output
    "outDir": "./dist",
    "rootDir": "./src",
    "declaration": true,
    "declarationMap": true,
    "sourceMap": true,

    // Skip Lib Check
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist", "**/*.test.ts"]
}
```

---

## **Type Definition Structure**

### **src/types/index.ts**
```typescript
// Central location for all type definitions

export interface User {
  id: string;
  email: string;
  name: string;
  role: 'admin' | 'organizer' | 'member';
  status: 'online' | 'offline' | 'studying';
  createdAt: Date;
  updatedAt: Date;
}

export interface StudyGroup {
  id: string;
  name: string;
  description: string;
  organizerId: string;
  createdAt: Date;
  updatedAt: Date;
}

export interface Session {
  id: string;
  groupId: string;
  topicId: string;
  title: string;
  scheduledAt: Date;
  durationMinutes: number;
  capacity: number;
  status: 'scheduled' | 'ongoing' | 'completed';
  createdAt: Date;
  updatedAt: Date;
}

// Add more as needed
```

---

## **API Request/Response Types**

### **src/types/api.ts**
```typescript
// Standardized API responses

export interface ApiResponse<T> {
  success: boolean;
  data?: T;
  error?: {
    code: string;
    message: string;
  };
  timestamp: Date;
}

export interface PaginatedResponse<T> {
  items: T[];
  total: number;
  page: number;
  limit: number;
  hasMore: boolean;
}

export interface AuthResponse {
  accessToken: string;
  refreshToken: string;
  user: User;
}
```

---

## **Express Request/Response Types**

### **src/types/express.ts**
```typescript
import { Request, Response } from 'express';

export interface AuthenticatedRequest extends Request {
  user?: {
    id: string;
    email: string;
    role: string;
  };
}

export interface TypedResponse<T> extends Response {
  json(body: ApiResponse<T>): this;
}
```

---

## **ESLint Configuration for TypeScript**

### **.eslintrc.json**
```json
{
  "parser": "@typescript-eslint/parser",
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "prettier"
  ],
  "plugins": ["@typescript-eslint"],
  "rules": {
    "@typescript-eslint/no-explicit-any": "error",
    "@typescript-eslint/explicit-function-return-types": "warn",
    "@typescript-eslint/no-unused-vars": ["error", {
      "argsIgnorePattern": "^_"
    }]
  }
}
```

---

## **Key TypeScript Best Practices**

### **1. Avoid `any`**
```typescript
// ❌ Bad
function processData(data: any) {
  return data.name;
}

// ✅ Good
interface UserData {
  name: string;
}

function processData(data: UserData) {
  return data.name;
}
```

### **2. Use Interfaces for Contracts**
```typescript
// ✅ Good
interface UserRepository {
  findById(id: string): Promise<User | null>;
  create(user: CreateUserInput): Promise<User>;
}
```

### **3. Type Database Models**
```typescript
// ✅ Good
class User {
  id: string;
  email: string;
  password: string;
  
  constructor(data: CreateUserInput) {
    this.id = generateId();
    this.email = data.email;
    this.password = hashPassword(data.password);
  }
}
```

### **4. Explicit Return Types**
```typescript
// ✅ Good
async function getUserById(id: string): Promise<User | null> {
  return await User.findById(id);
}

// Better for APIs
function validateEmail(email: string): boolean {
  return email.includes('@');
}
```

### **5. Use Enums for Constants**
```typescript
// ✅ Good
enum UserRole {
  ADMIN = 'admin',
  ORGANIZER = 'organizer',
  MEMBER = 'member'
}

interface User {
  role: UserRole;
}
```

---

## **Learning Resources**

- [TypeScript Handbook](https://www.typescriptlang.org/docs/) - Official documentation
- [TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html) - Google's style guide
- [Effective TypeScript](https://effectivetypescript.com/) - Best practices book

---

**Status:** Use this configuration from Phase 1, Task 1.7

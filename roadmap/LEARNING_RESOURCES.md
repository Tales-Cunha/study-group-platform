# Learning Resources (Context7)

**Guide:** Use these resources when tackling each phase's topics

---

## **Phase 1: Foundation & CI/CD**

### **TypeScript Configuration**
- **Reference:** `/websites/typescriptlang` (Official TypeScript docs, benchmark: 91.3)
- **Reference:** `/websites/ts_dev-style` (Google's TypeScript Style Guide)

### **Node.js & Async/Await**
- **Reference:** `/nodejs/node` (Official Node.js runtime docs)
- **Reference:** `/goldbergyoni/nodebestpractices` (Node.js Best Practices collection)

### **Docker & Containerization**
- **Official Docker Docs:** https://docs.docker.com/
- **docker-compose:** https://docs.docker.com/compose/

### **Jest Testing Framework**
- **Official Jest Docs:** https://jestjs.io/docs/getting-started
- **TypeScript + Jest:** https://jestjs.io/docs/getting-started#using-typescript

### **PostgreSQL**
- **Official PostgreSQL:** https://www.postgresql.org/docs/
- **Sequelize ORM:** https://sequelize.org/docs/v6/

### **GitHub Actions**
- **Official Guide:** https://docs.github.com/en/actions
- **Workflow Syntax:** https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions

### **Winston Logger**
- **Official Winston:** https://github.com/winstonjs/winston
- **Structured Logging:** https://www.splunk.com/en_us/data-insider/what-is-structured-logging.html

---

## **Phase 2: Authentication & Authorization**

### **JWT (JSON Web Tokens)**
- **JWT.io:** https://jwt.io/introduction
- **Auth0 JWT Handbook:** https://auth0.com/resources/ebooks/jwt-handbook
- **Best Practices:** https://tools.ietf.org/html/rfc7519

### **Password Hashing (bcrypt)**
- **bcrypt Package:** https://www.npmjs.com/package/bcrypt
- **OWASP Cheat Sheet:** https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html

### **OAuth 2.0**
- **OAuth Specification:** https://oauth.net/2/
- **Authorization Code Flow:** https://oauth.net/2/grant-types/authorization-code/
- **Passport.js Google Strategy:** http://www.passportjs.org/packages/passport-google-oauth2/

### **Input Validation (Joi/Zod)**
- **Joi Documentation:** https://joi.dev/
- **Zod Documentation:** https://zod.dev/

### **RBAC (Role-Based Access Control)**
- **OWASP Authorization:** https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html
- **RBAC Pattern:** https://en.wikipedia.org/wiki/Role-based_access_control

---

## **Phase 3: Groups & Sessions + Caching**

### **Relational Database Design**
- **Database Design Fundamentals:** https://en.wikipedia.org/wiki/Relational_database
- **Sequelize Associations:** https://sequelize.org/docs/v6/core-concepts/assocs/

### **Many-to-Many Relationships**
- **Junction Tables:** https://www.1keydata.com/database-normalization/many-to-many.php
- **Sequelize Many-to-Many:** https://sequelize.org/docs/v6/core-concepts/assocs/#many-to-many-associations

### **Redis Caching**
- **Official Redis:** https://redis.io/docs/
- **ioredis Library:** https://github.com/luin/ioredis
- **Cache-Aside Pattern:** https://docs.microsoft.com/en-us/azure/architecture/patterns/cache-aside

### **Pagination**
- **REST Pagination Best Practices:** https://www.elastic.co/guide/en/elasticsearch/reference/current/paginate-search-results.html
- **Offset vs Cursor:** https://use-the-index-luke.com/no-offset

### **DateTime Handling**
- **date-fns:** https://date-fns.org/
- **Moment.js:** https://momentjs.com/
- **Timezone Considerations:** https://www.timeanddate.com/

---

## **Phase 4: Notes & Cache Invalidation**

### **Cache Invalidation (CRITICAL)**
- **Cache Invalidation Article:** https://blog.logrocket.com/methods-for-cache-invalidation/
- **"Two Hard Problems in CS":** https://www.karlton.as/2017/12/13/cache-invalidation/
- **Strategies:** https://en.wikipedia.org/wiki/Cache_replacement_policies

### **PostgreSQL Full-Text Search**
- **PostgreSQL FTS:** https://www.postgresql.org/docs/current/textsearch.html
- **Query Optimization:** https://www.postgresql.org/docs/current/sql-explain.html

### **Markdown Processing**
- **markdown-it:** https://github.com/markdown-it/markdown-it
- **Markdown Spec:** https://spec.commonmark.org/

### **XSS Prevention**
- **OWASP XSS:** https://owasp.org/www-community/attacks/xss/
- **sanitize-html:** https://github.com/apostrophecms/sanitize-html
- **DOMPurify:** https://github.com/cure53/DOMPurify

### **Query Performance**
- **EXPLAIN ANALYZE:** https://www.postgresql.org/docs/current/sql-explain.html
- **Database Indexing:** https://use-the-index-luke.com/

---

## **Phase 5: Real-Time Features & Kafka**

### **WebSockets**
- **RFC 6455:** https://tools.ietf.org/html/rfc6455
- **Socket.io Documentation:** https://socket.io/docs/

### **Socket.io**
- **Socket.io Rooms:** https://socket.io/docs/v4/rooms/
- **Socket.io Adapters:** https://socket.io/docs/v4/socket-io-redis/
- **Socket.io Events:** https://socket.io/docs/v4/emit-cheatsheet/

### **Kafka**
- **Official Kafka:** https://kafka.apache.org/documentation/
- **Kafka Concepts:** https://kafka.apache.org/intro
- **kafkajs Library:** https://kafka.js.org/

### **Event-Driven Architecture**
- **Martin Fowler:** https://martinfowler.com/articles/201701-event-driven.html
- **Event Sourcing:** https://martinfowler.com/eaaDev/EventSourcing.html

### **Producer-Consumer Pattern**
- **Design Patterns:** https://www.yusufcanb.com/post/producer-consumer-pattern-in-nodejs
- **Message Queues:** https://en.wikipedia.org/wiki/Message_queue

---

## **Phase 6: Progress & Workers**

### **Background Jobs**
- **Bull Queue:** https://github.com/OptimalBits/bull (alternative to Kafka)
- **Kafka Consumers:** https://kafka.js.org/docs/consumer

### **Analytics & Aggregation**
- **Aggregation Pipelines:** https://docs.mongodb.com/manual/aggregation/
- **Data Warehouse Concepts:** https://en.wikipedia.org/wiki/Data_warehouse

### **Idempotency**
- **Idempotency Patterns:** https://www.callicoder.com/http-methods-idempotent-safe/
- **Exactly-Once Semantics:** https://kafka.apache.org/documentation/#semantics

### **Dead Letter Queues**
- **DLQ Pattern:** https://en.wikipedia.org/wiki/Dead_letter_queue
- **Error Handling:** https://kafka.js.org/docs/retry-and-timeout

---

## **Phase 7: AWS Deployment**

### **AWS Fundamentals**
- **AWS Documentation:** https://docs.aws.amazon.com/
- **AWS EC2:** https://docs.aws.amazon.com/ec2/
- **AWS RDS:** https://docs.aws.amazon.com/rds/

### **CI/CD to AWS**
- **GitHub Actions AWS:** https://github.com/actions/deploy-to-aws-cloudformation
- **GitHub Deploy Action:** https://github.com/appleboy/ssh-action
- **Blue-Green Deployments:** https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/

### **CloudWatch**
- **CloudWatch Logs:** https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/
- **CloudWatch Metrics:** https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/

### **Secrets Management**
- **AWS Secrets Manager:** https://docs.aws.amazon.com/secretsmanager/
- **Environment Variables:** https://docs.aws.amazon.com/amplify/latest/userguide/environment-variables.html

---

## **Phase 8: Optimization & Security**

### **Query Optimization**
- **PostgreSQL EXPLAIN:** https://www.postgresql.org/docs/current/sql-explain.html
- **Index Strategies:** https://use-the-index-luke.com/
- **N+1 Problem:** https://medium.com/@bretdoucette/explaining-the-n-1-query-problem-1f21f577eac

### **Security (OWASP Top 10)**
- **OWASP Top 10:** https://owasp.org/Top10/
- **SQL Injection:** https://owasp.org/www-community/attacks/SQL_Injection
- **XSS Prevention:** https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html
- **CORS Security:** https://owasp.org/www-community/attacks/cors_abuse

### **Performance Testing**
- **Artillery.io:** https://artillery.io/
- **K6 Load Testing:** https://k6.io/
- **Load Testing Guide:** https://en.wikipedia.org/wiki/Load_testing

### **API Documentation**
- **OpenAPI/Swagger:** https://swagger.io/specification/
- **Swagger UI:** https://swagger.io/tools/swagger-ui/

### **Code Quality**
- **ESLint:** https://eslint.org/
- **Prettier:** https://prettier.io/
- **SonarQube:** https://www.sonarqube.org/

---

## **General Backend Learning**

### **Node.js Best Practices**
- **Reference:** `/goldbergyoni/nodebestpractices` (High reputation, 734+ snippets)
- **Official Node.js Docs:** `/websites/nodejs_api` (80.8 benchmark score)

### **TypeScript Mastery**
- **Reference:** `/websites/typescriptlang` (Official, 91.3 benchmark score)
- **Reference:** `/microsoft/typescript` (18,942 code snippets)

### **RESTful API Design**
- **REST API Best Practices:** https://restfulapi.net/
- **REST Maturity Model:** https://restfulapi.net/richardson-maturity-model/

### **Database Design**
- **Normalization:** https://en.wikipedia.org/wiki/Database_normalization
- **ACID Properties:** https://en.wikipedia.org/wiki/ACID

### **System Design**
- **System Design Primer:** https://github.com/donnemartin/system-design-primer
- **Distributed Systems:** https://en.wikipedia.org/wiki/Distributed_computing

---

**Note:** Use Context7 lookups in each phase for the most current resources  
**Format:** When questions arise, use `/context7_query-docs` with the specific libraryId

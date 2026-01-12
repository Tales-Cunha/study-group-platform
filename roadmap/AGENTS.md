# AGENTS.md

**Guidelines for AI/Agent Assistance on This Project**

---

## **📋 Project Context**

**Project Name:** Study Group Platform  
**Backend Focus:** Learning backend architecture, database design, API security, real-time systems  
**Duration:** 16 weeks (8 phases)  
**Tech Stack:** Node.js + Express + TypeScript + PostgreSQL + Redis + Kafka + Docker + AWS  

---

## **🎯 What You Can Help With**

### **Code Writing Tasks**
- Implementing individual functions/endpoints
- Writing test cases (unit and integration)
- Refactoring existing code
- Bug fixes within a task
- TypeScript type definitions

### **Design & Architecture**
- Reviewing code structure
- Suggesting improvements
- TypeScript strict mode enforcement
- Design pattern application

### **Documentation**
- Code comments for complex logic
- Updating phase documentation
- Creating API response examples
- Writing test scenarios

### **Learning Support**
- Explaining concepts
- Pointing to resources
- Suggesting learning approaches
- Code review feedback

---

## **❌ What You Should NOT Do**

- **Don't skip tests:** Always TDD - write tests first
- **Don't violate TypeScript strict mode:** No `any`, all types explicit
- **Don't commit code without approval:** Follow task approval criteria
- **Don't refactor beyond task scope:** Stay focused on current task
- **Don't create features outside current phase:** Stick to roadmap
- **Don't skip documentation:** Update docs as you go

---

## **📝 How to Request Help**

### **For Code Implementation:**
```
I'm working on Phase X, Task X.Y: [Task Name]
Approval Criteria:
- [ ] Criterion 1
- [ ] Criterion 2

I need help with: [specific part]
```

### **For Debugging:**
```
Task: [Name]
Error: [error message]
Code: [relevant snippet]
What am I missing?
```

### **For Design Review:**
```
I've implemented [feature]
Can you review: [code link or snippet]
Should I approach this differently?
```

---

## **📂 Project File Structure**

```
study-group-backend/
├── src/
│   ├── features/
│   │   ├── auth/
│   │   ├── groups/
│   │   ├── sessions/
│   │   ├── notes/
│   │   └── ...
│   ├── shared/
│   │   ├── middleware/
│   │   ├── utils/
│   │   ├── guards/
│   │   ├── database/
│   │   └── socket/
│   ├── config/
│   └── app.ts
├── tests/
├── docker/
└── roadmap/
```

---

## **🔑 Key Principles**

1. **TDD First:** Write tests before code
2. **TypeScript Strict:** No implicit types, no `any`
3. **Task Focused:** Complete current task before next
4. **Quality Over Speed:** Code quality > rapid implementation
5. **Documentation:** Comments for complex logic
6. **Testing:** All functionality tested (70%+ coverage goal)

---

## **✅ Task Completion Checklist**

Before considering a task done:
- [ ] All approval criteria met
- [ ] Tests written and passing
- [ ] Code follows TypeScript strict mode
- [ ] No console.log (use logger)
- [ ] Comments explain complex logic
- [ ] No dead code
- [ ] Documentation updated
- [ ] Linting passes
- [ ] Ready for code review

---

## **🚨 Common Issues & Solutions**

### **Issue: Tests not catching bugs**
**Solution:** Tests are too shallow. Go deeper - test edge cases, error scenarios, business logic.

### **Issue: TypeScript compilation errors**
**Solution:** Don't suppress errors. Fix the root cause. Ask if you're not sure about types.

### **Issue: Cache invalidation not working**
**Solution:** This is hard! Ensure ALL related caches are cleared. Test explicitly that no stale data returns.

### **Issue: Real-time updates not reaching users**
**Solution:** Check socket room membership. Add logging. Use Socket.io test utilities.

---

## **📞 When to Ask for Help**

✅ **Ask when:**
- Stuck on implementation for >30 minutes
- Unsure about TypeScript types
- Not sure how tests should work
- Design decision unclear
- Performance issue detected

❌ **Don't ask for:**
- Non-work-related questions
- Things easily found in docs
- Complete code for a task (learn by doing!)

---

## **🎓 Learning vs. Doing**

**This is a learning project.** Balance:
- **30% Writing code** - Implement features
- **30% Writing tests** - Ensure quality
- **20% Learning** - Study topics in LEARNING_RESOURCES.md
- **20% Debugging** - Fix issues, understand problems

Don't skip learning just to go fast. Understanding > speed.

---

## **📊 Success Metrics**

Track your progress:
- ✅ Phases completed (target: 8/8)
- ✅ Test coverage (target: 70%+)
- ✅ Code quality (linting, formatting)
- ✅ Security audit passed
- ✅ Deployed to AWS
- ✅ Learning outcomes achieved

---

## **Notes & Reminders**

- Always check the roadmap first
- Read approval criteria before starting
- Use Context7 for learning resources
- Reference RULES.md for conventions
- Keep tasks atomic (2-4 hours each)
- Don't accumulate tech debt

---

**Created:** [Date]  
**Last Updated:** [Date]  
**Ready to work together!** 🚀

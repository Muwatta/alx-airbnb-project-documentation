## File: flowcharts/registration-flow.md

# Flowchart: User Registration (draw in Draw.io)

Flow steps:
1. Start
2. User submits registration form (email, password, name)
3. Validate inputs
4. If invalid -> return validation error -> End
5. Check if email already exists
6. If exists -> return "email already in use" -> End
7. Hash password (bcrypt)
8. Save user record to users table
9. Generate verification email (optional)
10. Generate JWT token
11. Return success + token
12. End



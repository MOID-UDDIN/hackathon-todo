# Feature Spec — Backend Auth (JWT)

## Summary
Implement backend authentication for a multi-user todo app using JWT tokens.

## Goals
- Users can sign up, log in, and log out.
- JWT tokens are generated and validated correctly.
- Passwords are hashed (bcrypt).
- Token decode verifies algorithm.

## Non-Goals
- OAuth providers
- Refresh tokens (unless already implemented)
- Role-based access control

## API Requirements (Expected)
- `POST /auth/signup` — create user
- `POST /auth/login` — returns JWT token
- `POST /auth/logout` — client-side token discard; optional server-side tracking
- `GET /auth/me` — returns current user profile (optional if exists)

## Data Requirements
- `User` model includes:
  - id (primary key)
  - email (unique)
  - hashed_password
  - created_at

## Security Requirements
- JWT signed with `JWT_SECRET` env var.
- Tokens include `sub`, `exp`, `iat`, `jti`.
- Verify algorithm is HS256.

## Acceptance Criteria
- Signup creates user and stores hashed password.
- Login returns a valid token.
- Protected routes reject missing/invalid token.
- Logout clears session from frontend (backend endpoint optional but supported).

## Edge Cases
- Duplicate email signup returns error.
- Wrong password returns error.
- Expired token returns 401.
- Missing env vars fails fast.

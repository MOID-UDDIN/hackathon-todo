# Plan — Backend Auth (JWT)

## Implementation Outline
1. Confirm `security.py`:
   - bcrypt 72 byte safe
   - create_access_token with exp/iat/jti
   - decode_token verifies HS256
2. Confirm auth routes exist:
   - signup/login/logout/me (as implemented)
3. Confirm dependency injection:
   - `get_current_user` decodes token and loads user
4. Add/verify error handling:
   - duplicate email
   - invalid password
   - invalid token
5. Smoke test via curl/Postman:
   - signup → login → access protected route → logout

## Files Expected (Typical)
- `backend/app/core/security.py`
- `backend/app/api/routes/auth.py`
- `backend/app/api/deps.py`
- `backend/app/models/user.py` or `backend/app/models.py` (your project layout)

## Done When
- Token generation works and frontend can authenticate using it.

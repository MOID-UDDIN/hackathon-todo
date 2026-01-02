# Requirements Checklist — Backend Auth

## Must Have
- [x] JWT signing with env secret
- [x] Password hashing (bcrypt)
- [x] Login returns token
- [x] Protected routes enforce auth
- [x] Errors returned for invalid login/signup

## Should Have
- [ ] `/auth/me` endpoint for profile
- [ ] Consistent error schema

## Not Needed
- [ ] OAuth
- [ ] Refresh tokens
- [ ] RBAC

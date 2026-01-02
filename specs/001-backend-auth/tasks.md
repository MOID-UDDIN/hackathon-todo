# Tasks — Backend Auth (JWT)

- [ ] T001 Verify `JWT_SECRET` is loaded from env in backend config
- [ ] T002 Verify `security.py` creates token with `sub`, `exp`, `iat`, `jti`
- [ ] T003 Verify bcrypt hashing + verify is correct and safe
- [ ] T004 Verify auth routes: signup/login/logout
- [ ] T005 Verify `get_current_user` rejects invalid/expired token
- [ ] T006 Add/update minimal docs in README or architecture if needed
- [ ] T007 Run smoke tests: signup → login → protected → logout

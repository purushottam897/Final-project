# TODO List for Troubleshooting and Fixing Database Table Mismatch Errors

## Step 1: Backend Integration Tests
- [ ] Create or run existing automated tests to verify user-related endpoints (login, create, update, fetch).
- [ ] Test endpoints for entities related to User (Cart, Learning, Progress).
- [ ] Validate response correctness and error handling.

## Step 2: Backend Runtime Logs and SQL Error Investigation
- [ ] Enable detailed Hibernate SQL logging (`spring.jpa.show-sql=true`, logging.level.org.hibernate=DEBUG).
- [ ] Collect logs during frontend API calls to identify SQL errors or exceptions.
- [ ] Trace exceptions back to source for fixes.

## Step 3: Frontend API Call and Response Verification
- [ ] Review frontend network calls using browser devtools.
- [ ] Confirm API URLs match backend routes.
- [ ] Validate responses and error messages.
- [ ] Fix mismatches or errors in endpoints or payloads.

## Step 4: Improved Backend Logging and Error Messages
- [ ] Add fine-grained logging around database access areas.
- [ ] Catch and log exceptions with detailed context.
- [ ] Provide meaningful error responses for easier client-side diagnosis.

## Step 5: Environment & Cache Validation
- [ ] Clear Hibernate 2nd-level and query caches.
- [ ] Restart backend services after schema or data updates.
- [ ] Recheck database connections and permissions.

## Optional Enhancements
- [ ] Use Database migration tools like Flyway or Liquibase for schema management.
- [ ] Implement full-stack tests (e2e) covering common user workflows.

---

# Please mark tasks as done as you proceed. I can assist with implementation or testing for any step as needed.

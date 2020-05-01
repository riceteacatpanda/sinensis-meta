# Technical

### Structure
Single Page app and API based system
* Go (?) API
* React/Vue frontend

### Storage
 * MongoDB longterm storage for user information, etc
   * Consider Redis for submission storage/other high demand functions

### Authentication
 * TOTP for apps like Google authenticator
 * JWT in place of a typical session cookie
   * Contains basic user information like UID, team name, etc

### Security considerations
 * Query injection (is that even possible with Mongo?)
 * XSS and CSRF
 * Cookie sharing/theft

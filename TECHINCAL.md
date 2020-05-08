# Technical

### Structure
Single Page app and API based system
* Go API
   * Cannot use standard lib HTTP router as it lacks basic functionality like verbs
   * Routing with [gorilla/mux](https://github.com/gorilla/mux) or [go-chi/chi](https://www.github.com/go-chi/chi)?
* Vue frontend
   * Built from the ground up using Vue, .vue files and Node.JS on the development side, to then be built with Node into a series of static files good for deployment.
   * Consistent usage of .vue files to split pages into separate items reduces bulk in components like CSS, especially because all CSS is scoped - it only affects the component it is written for.
   * Removing old/unused CSS also becomes easier as you know exactly what is using it

### Storage
 * Persistent storage candidates
   * MySQL
   * MongoDB
     * JSON based, more suited to OOP
     * Has an [official Go driver](https://docs.mongodb.com/drivers/go)
 * ~~Consider Redis for submission cache?~~ During Houseplant CTF thee were an average of 13 submissions a minute, which isn't especially strenuous and can easily run off the main persistent storage

### Authentication
 * TOTP for apps like Google authenticator
   * Various implementations, eg [pquerna/otp](https://github.com/pquerna/otp/)
 * JWT in place of a typical session cookie
   * Contains basic user information like UID, team name, etc
   * Makes SPA more independent from API hence reducing server load and bandwidth usage
   * [dgrijalva/jwt-go](https://github.com/dgrijalva/jwt-go) is the most popular Go JWT library

### Security considerations
 * Query injection (is that even possible with Mongo?)
 * XSS and CSRF
 * Cookie sharing/theft

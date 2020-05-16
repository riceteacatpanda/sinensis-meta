# Technical

### Structure
Single Page app and API based system
* Go API
   * Cannot use standard lib HTTP router as it lacks basic functionality like verbs
   * Routing with [gorilla/mux](https://github.com/gorilla/mux)
* Vue frontend
   * Built from the ground up using Vue, .vue files and Node.JS for development
   * Compiles into static HTML to be served with NGINX or whatever
   * Consistent usage of .vue files to split pages into separate items reduces bulk in components like CSS, especially because all CSS is scoped - it only affects the component it is written for.
   * Removing old/unused CSS also becomes easier as you know exactly what is using it

### Storage
 * MySQL or SQL-based equialent as opposed to MongoDB

### Authentication
 * TOTP as a secondary goal
   * Various implementations available, eg [pquerna/otp](https://github.com/pquerna/otp/)
 * JWT in place of a typical session cookie
   * Will contain only static information that never changes to prevent information going out of date
   * Items like UUIDs and team IDs
   * [dgrijalva/jwt-go](https://github.com/dgrijalva/jwt-go) is the most popular Go JWT library

### Security considerations
 * Query injection (is that even possible with Mongo?)
 * XSS and CSRF
 * Cookie sharing/theft

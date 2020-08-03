# Technical

### Structure
Single Page app and API based system
* Go API
   * Cannot use standard lib HTTP router as it lacks basic functionality like verbs
   * Routing with [gofiber/fiber](https://github.com/gofiber/fiber)
* React frontend
   * Compiles into static HTML to be served with NGINX or whatever

### Storage
 * MySQL for development or compatible equivalent

### Authentication
 * TOTP as a secondary goal
   * Various implementations available, eg [pquerna/otp](https://github.com/pquerna/otp/)
 * JWT in place of a typical session cookie
   * Will contain only static information that never changes to prevent information going out of date
   * Contains only isAdmin, user ID and username
   * [dgrijalva/jwt-go](https://github.com/dgrijalva/jwt-go) is the most popular Go JWT library

### Security considerations
 * ~~Query injection (is that even possible with Mongo?)~~ Can't inject SQL when you're not even writing SQL yourself :sunglasses:
 * XSS and CSRF
 * Cookie sharing/theft

### Easter eggs
https://frenxi.com/http-headers-you-dont-expect/

> [23:21] Vi-『han burger』: Oh very important thing that I forgot to mention on the call! We need to make it so /wp-admin redirects to a rickroll in order to troll hackers - this is a critical top priority feature

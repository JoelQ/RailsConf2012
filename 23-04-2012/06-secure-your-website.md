# Secure your website
## How secure does my site need to be?

### SQL injection
* Don't put params directly into active record methods
* Sanitize all SQL input

### XSS
* Secure your cookies using options
* httponly: false (false by default, cannot be read by javascript)
* secure: false (use ssl)
* Escape all input

### Session management
* preventing the stealing of sessions
`cookie_store`, `cache_store`, `active_record_store1`
* `secret_token`, make sure it is secure
* XSS, insecure networks can be used to steal session
* use `force_ssl`
* Allow users to logout, give a log out link
* Timeout sessions (default when close browser)
* Do not allow concurrent logins
* Lockout accounts after x-number of failed login attempts
* Password Complexity, enforce minimum complexity
* Destroy session on logout
* `reset_session` does not kill the session
* Encrypt all stored passwords
* Use bcrypt over md5 or SHA (much harder/slower to decrypt)
* No large objects as cookies
* Don't store critical data in cookies/session

### Mass Assignment
* `attr_protected`, not the best way
* `attr_accessible`, better to use whitelist over blacklist
* `attr_accessible` can be scoped `as: :admin`
* fix in controller with private method that slices params (known as slice pattern)
* `strong_parameters` gem

### Direct object reference
* Find current user first
* use current_user.find methods to only return the user's own objects
* use scoping/authorization

### CSRF
* Use correct HTTP verbs
* GET requests for safe actions
* Destructive/changing actions should use other request types
* use rails csrf `authenticity_token` with `protect_from_forgery`

### Redirection and file uploads
* redirecting to a location from `params`
* don't set the url relocation in `params`, use cookie or session
* sanitize any file inports
* sanitize file types
* Process Asynchronously


### SSL
* slight pain but use everywhere possible
* set ssl ciphers
* set ssl protocols


### Admin and intranet
* XSS/CSRF/injection - sanitize even though its an admin interface
* Don't assume anything just because it is admin
* use IP whitelisting

### Info leakage
* give out the least possible info about your architecture/software versions
* strip headers

### Server side
* user priveleges - set permissions/authorizations
* enforce good passwords
* don't show parameters in the log files
* obscure sensitive data

### Resources
* `guides.rubyonrails.or/security.html`
* `www.rorsecurity.info`
* `brakemanscanner.org` gem
* tarantula gem for fuzz testing
* `www.owasp.org` general resource on security (not rails specific)

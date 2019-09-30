# USER

In order to access user specific functionality of InterMine like fetching private lists or uploading lists, one must be connected to the specific mine instance as an authenticated user

## AUTHENTICATED SERVICE
```javascript
const intermine = require('imjs')
// To create an authenticated service class
const authenticatedFlymine = new intermine.Service({
    root: 'www.flymine.org/query',
    token: ...                      // User token, to be obtained from your profile page
})

// In case you want to authorize an unauthorized service, use the connectAs option
// It returns the service with same root but connected as a different user

token = ...     // Token used to authorize the flymine
authenticatedFlymine = unauthenticatedFlymine.connectAs(token)
```

## USER METHOD 
`imjs` also provides `User` class to represent the authenticated user's profile information and manipulate it

```javascript
const intermine = require('imjs')
const flymine = new intermine.Service({
    root: 'www.flymine.org/query'
})
const me = new User(flymine, {
    username: ...                   // User's login name
})

// In order to set preferences, or clear them use the following methods
me.setPreference(key, value, (err, data) => {
    if(err) {
        // Something unexpected has happened, perform error handling here
        return;
    }
    // Preference set successfully...
})

me.clearPreference(key, (err, data) => {
    if(err) {
        // Something unexpected has happened, perform error handling here
        return;
    }
    // Preference cleared successfully...
})

// Using the User class, one can also create or revoke tokens in order to authenticate the Service
// First argument denotes the type of token to be created
me.createToken('day').then(newToken => {
    // Do something with the new token (like create a new Service with it)
})

// To delete all tokens
me.revokeAllTokens.then(() => {
    // Do something, after revoking all tokens
    // Preferrably clear of the authenticatd mine instances
})
```

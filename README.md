# Guava
Simple web backend language.
    
Tokenize (with regex), parser (into parse tree), interpret (treat as instructions to a separate machine)

Let's see if I can handle web requests with a Ruby webserver

idk how SQL works but ideally it would interact with that

Guava allows you to determine behaviour upon receiving any [HTTP request method](https://en.m.wikipedia.org/wiki/HTTP#Request_methods)

```
import user_profile_page from "user_profile.gml"; // gml (guava markup language) are HTML templates
import error_page from "404.gml";

let db = sql_connect(...);

if (db.connect_error) {
    quit("Could not connect to SQL database.");
}

@GET {

    (username=*) -> {

        let users = db.poll("SELECT TOP 1 * FROM Users WHERE Username=" + username);
    
        if (users.length == 1) {
            reply user_profile_page(users[0]);
        } else {
            reply error_page("We couldn't find that user.");
        }
    }

    (*) -> {
        reply error_page("Invalid request.");
    }
}
```

# Guava
Simple web backend language.
    
Tokenize (with regex), parser (into parse tree), interpret (treat as instructions to a separate machine)

Let's see if I can handle web requests with a Ruby webserver

idk how SQL works but ideally it would interact with that

```
import user_profile_page from "user_profile.gml"; // gml (guava markup language) are HTML templates
import error_page from "404.gml";

@GET {

    (username=*) {

        let users = SELECT TOP 1 * FROM Users WHERE Username=username;
    
        if (users.length == 1) {
            reply user_profile_page(user);
        } else {
            reply error_page("We couldn't find that user.");
        }
    }

    (*) {
        reply error_page("Invalid request.");
    }
}
```

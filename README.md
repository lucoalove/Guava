# Guava
Simple web backend language.
    
Tokenize (with regex), parser (into parse tree), interpret (treat as instructions to a separate machine)

Let's see if I can handle web requests with a Ruby webserver

idk how SQL works but ideally it would interact with that

```
import user_profile_page from "user_profile.gml"; // gml (guava markup language) are HTML templates
import error_page from "404.gml";

onrequest "GET" : req -> {

    SELECT req["user"] FROM Users {

        []    -> reply error_page("We couldn't find that user.");
        users -> reply user_profile_page(users[0]);
    }
}
```

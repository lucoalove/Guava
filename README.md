# Guava
Simple web backend language.
    
Tokenize (with regex), parser (into parse tree), interpret (treat as instructions to a separate machine)

Let's see if I can handle web requests with a Ruby webserver



```
import db from "your/db/repository/";
import user_profile_page from "user_profile.gml"; // gml (guava markup language) are HTML templates
import error_page from "404.gml";

onrequest "GET" | (req) -> {

    find req["username"] in db {

        KEY_UNDEFINED -> reply error_page("Invalid request. Please try again.");
        KEY_NOT_FOUND -> reply error_page("We couldn't find that user.");
        user          -> reply user_profile_page(user);
    }
}
```

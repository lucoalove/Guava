# Guava
Simple web backend language.
    
Tokenize (with regex), parser (into parse tree), interpret (treat as instructions to a separate machine)

Let's see if I can handle web requests with a Ruby webserver

```
import db from "your/db/repository/";
import image_page from "gallery.html";
import error_page from "404.html";

onrequest "GET" | (request_json) -> {

  if (request_json.contains("img") and db["images"].contains(request_json["img"])) {
    // also put in data from db
    reply image_page;
  } else {
    reply error_page;
  }
}
```

!SLIDE bullets incremental
# REST - Roy Fielding #

* Roy Fielding: een van de bedenkers van HTTP
* [Dissertation](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
* *RE*presentatational *S*tate *T*ransfer

!SLIDE bullets incremental
# REST Constraints #

* Uniform Interface
* Stateless
* Cacheable
* Client-Server
* Layered System
* Code on Demand (optional)

!SLIDE bullets
# REST Constraints - Stateless #

* Uniform Interface
* **Stateless**
* Cacheable
* Client-Server
* Layered System
* Code on Demand (optional)

!SLIDE bullets incremental
# REST Constraints - Stateless #

* Alle data zit in het request.
* Alle data zit in het response.
* Clients **hoeven** nooit iets op te slaan of te onthouden (ook geen cookies)

!SLIDE bullets
# REST Constraints - Cachable #

* Uniform Interface
* Stateless
* **Cacheable**
* Client-Server
* Layered System
* Code on Demand (optional)

!SLIDE bullets incremental
# REST Constraints - Cachable #

* Clients en servers kunnen cache onderhandelen.
* Proxies kunnen cachen.
* GET, HEAD, OPTIONS. Niet PATCH, PUT, POST of DELETE.

!SLIDE code

    curl -i http://localhost:3000/toilet-locations/63a4a8ce-191f-4812-b242-6093139c879e

    curl -H 'If-None-Match: W/"aa2d5488ac813807a86ef275b4fbf85a"' -i http://localhost:3000/toilet-locations/63a4a8ce-191f-4812-b242-6093139c879e

!SLIDE bullets
# REST Constraints - Client-Server #

* Uniform Interface
* Stateless
* Cacheable
* **Client-Server**
* Layered System
* Code on Demand (optional)

!SLIDE bullets
# REST Constraints - Client-Server #

* Dat is het hele doel van een Web API.

!SLIDE bullets
# REST Constraints - Layered System #

* Uniform Interface
* Stateless
* Cacheable
* Client-Server
* **Layered System**
* Code on Demand (optional)

!SLIDE bullets
# REST Constraints - Layered System #

* Client ⟷ Applicatie
* Client ⟷  Proxy ⟷  Load Balancer ⟷  Webserver ⟷  Applicatie
* Is hetzelfde

!SLIDE bullets
# REST Constraints  - Uniform Interface #

* **Uniform Interface**
* Stateless
* Cacheable
* Client-Server
* Layered System
* Code on Demand (optional)

!SLIDE bullets incremental
# REST Constraints - Uniform Interface #

* Resource-Based
* Manipulation of Resources Through Representations
* Self-descriptive Messages
* Hypermedia as the Engine of Application State (HATEOAS)

!SLIDE bullets
# REST Constraints - Uniform Interface  - Resource Based #

* **Resource-Based**
* Manipulation of Resources Through Representations
* Self-descriptive Messages
* Hypermedia as the Engine of Application State (HATEOAS)

!SLIDE bullets incremental
# REST Constraints - Uniform Interface  - Resource Based #

* Interactie met Concepten en Domein models.
* Geen vervanging van een Database, maar abtractie daarvan.
* **Acties** op **Dingen**
* Niet **Acties**

!SLIDE bullets incremental
# Example

* We have toilet-location
* We want to add a rating
* What do we do?

!SLIDE code

   POST /toilet-locations/{id}/ratings
        { rating: { stars: 5 } }

VS

   POST /toilet-locations/rate
        { stars: 5 }

!SLIDE bullets
# REST Constraints - Uniform Interface  - Manipulation #

* Resource-Based
* **Manipulation of Resources Through Representations**
* Self-descriptive Messages
* Hypermedia as the Engine of Application State (HATEOAS)

!SLIDE bullets
# REST Constraints - Uniform Interface  - Manipulation #

* Wanneer een client een *weergave van een resource heeft*, inclusief metadata,
  heeft de client *genoeg informatie* om het te bewerken, vernieuwen of verwijderen.

!SLIDE code

    curl -s http://localhost:3000/toilet-locations/02472a1b-58c3-4e36-acc9-a593117b3642 | json_pp

!SLIDE bullets
# REST Constraints - Uniform Interface  - Self-descriptive #

* Resource-Based
* Manipulation of Resources Through Representations
* **Self-descriptive Messages**
* Hypermedia as the Engine of Application State (HATEOAS)

!SLIDE bullets incremental
# REST Constraints - Uniform Interface  - Self-descriptive #

* Alle informatie om te verwerken zit in het resource
* MIME-types
* Encoding
* Cacheability

!SLIDE code

    curl -s http://localhost:3000/toilet-locations/4b17022e-f581-4432-8549-f728776c0404 | json_pp

!SLIDE code

    curl -s -I http://localhost:3000/toilet-locations/02472a1b-58c3-4e36-acc9-a593117b3642

!SLIDE center

# [wat is dit?](https://twitter.com/berkes/status/734763358344339457)

!SLIDE bullets incremental

!SLIDE bullets
# Hypermedia

* media that has hyperlinks

!SLIDE bullets
# HATEOAS

> A REST client needs *no prior knowledge* about how to interact with any particular application or server beyond a *generic understanding of hypermedia*.

!SLIDE bullets
# Het voordeel van HATEOAS

> The HATEOAS constraint decouples client and server in a way that allows the server functionality to evolve independently.

!SLIDE bullets
# Engine of Application State

* [A state machine](https://twitter.com/berkes/status/734763358344339457)
* [Another State Machine](https://www.google.nl/?q=pager#safe=off&q=pager)

!SLIDE bullets incremental
# Hoe HATEOAS te implementeren?

* Links
* Interne documentatie, beschrijvende elementen
* OPTIONS

!SLIDE code

* curl -s http://localhost:3000/toilet-locations | json_pp

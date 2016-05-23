!SLIDE bullets incremental

# XML of JSON

* JSON. Het is de standaard

!SLIDE bullets incremental
# Of XML?

* Pro: compacter.
* Enige echt succesvolle RESTclient gebruikt... XML (okay, HTML)
* Con: extra DTDs of parsing instructies nodig.

!SLIDE code supplemental

`<avatar src="http://im.example.com/ab.png"
         changed_at="never"
         variant="small"
         height="200" width="300" />`
`<avatar src="http://im.example.com/ab.png"
         changed_at="never"
         variant="large"
         height="600" width="900" />`

!SLIDE code supplemental

    avatars: [
       {
          "src": "http://im.example.com/ab.png"
          "changed_at": "never",
          "variant": "small",
          "height": 200,
          "width: 300
       }
       {
          "src": "http://im.example.com/ab.png"
          "changed_at": "never",
          "variant": "large",
          "height": 600,
          "width: 900
       }
    ]

!SLIDE bullets incremental
# anti-bikeshedding: Jsonapi.org

* Opbouw van resources
* Opbouw van Errors
* Afhandelen van paging, sorting, filtering.

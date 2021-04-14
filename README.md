
# Linked Media Formats

Getting started with LOD can be overwhelming. An accessible starting place is to think about linking existing catalog records with external data sources and vocabularies. The goal is to connect records  that refer to the same work, person, or format by using unique, linked identifiers. 

## Schemas
How does LOD fit in to metadata? One widely used and well-documented structured data format is  schema.org, which includes fields for LOD. Here is their example for a [Movie](https://schema.org/Movie) in JSON-LD format, with linked data fields in bold:
<pre>
   {
      "@type": "Movie",
      "name": "The Hitchhiker's Guide to the Galaxy",
     <b> "titleEIDR": "10.5240/B752-5B47-DBBE-E5D4-5A3F-N",
      "editEIDR": "10.5240/0196-4177-FF62-A346-D0F6-Z",</b>
      "disambiguatingDescription": "VUDU version",
      "exampleOfWork":
        {
           "@type": "Movie",
            <b> "sameAs": "https://www.wikidata.org/wiki/Q836821"</b>
        }
      }
}</pre>

## Data Sources
As seen above [WikiData](https://wikidata.org/) and the [Entertainment Identifier Registry (EIDR)](https://ui.eidr.org/) are two stable sources of identifiers. These are the two recommended sources from the [FIAF LOD Task Force](LOD-Task%20Force). You can also search for other LOD vocabulary and authority sources on [BARTOC](http://bartoc.org/), for example those related to "[film](http://bartoc.org/vocabularies?search=film#)".

## LOD for Media Formats
We noticed that most writing on LOD for film and media focus on title and actor name authorities. We were curious about the implications for LOD for media formats and compiled the beginning of a list for reference.

### Film
 - **PBCore** provides LOD for gauged film formats in its [instantiationPhysical Film Vocabulary](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/).
     - [[8mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#8mmFilm), [9.5mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#9andaHalfmmFilm), [Super 8mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#Super8mmFilm), [16mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#16mmFilm), [Super 16mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#Super16mmFilm), [22mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#22mmFilm), [28mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#28mmFilm), [35mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#35mmFilm), [70mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#70mmFilm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#70mmFilm))]
     
 - **Getty AAT** provides LOD for members of its  \<size for photographic film> [term](http://vocab.getty.edu/aat/300263814):
     - [[8mm](http://vocab.getty.edu/aat/300263859), [16mm](http://vocab.getty.edu/aat/300263815), [Super 16mm](http://vocab.getty.edu/aat/300264669), [35mm](http://vocab.getty.edu/aat/300263816), [65mm](http://vocab.getty.edu/aat/300264670), [70mm](http://vocab.getty.edu/aat/300264672)] 
     
     
 - **WikiData** has entries for several sizes:
     - [[8mm](https://www.wikidata.org/wiki/Q270183), [16mm](https://www.wikidata.org/wiki/Q194383), [Super 16mm](https://www.wikidata.org/wiki/Q2713357)]

## Example Record
Here's an example of transforming an existing record



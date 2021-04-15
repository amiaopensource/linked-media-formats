

# Linked Media Formats

Getting started with LOD can be overwhelming. An accessible starting place is to think about linking existing catalog records with external data sources and vocabularies. The goal is to connect records  that refer to the same work, person, or format by using unique, linked identifiers.

## Intro
How does LOD fit in to metadata? One widely used and well-documented structured data format is [schema.org](schema.org), which includes fields for LOD. Here is their metadata example for a [Movie](https://schema.org/Movie) in JSON-LD format, with linked data fields in bold:
<pre>
{
     "@type": "Movie",
     <b>"@id": "https://www.wikidata.org/wiki/Q836821" </b>
     "name": "The Hitchhiker's Guide to the Galaxy",
     <b>"titleEIDR": "10.5240/B752-5B47-DBBE-E5D4-5A3F-N",</b>
     "disambiguatingDescription": "VUDU version",
}
</pre>

## Sources of Identifiers
As seen in the schema.org example above, [WikiData](https://wikidata.org/) and the [Entertainment Identifier Registry (EIDR)](https://ui.eidr.org/) are two stable sources of LOD identifiers. In fact, these are the two recommended sources from the [FIAF LOD Task Force](https://www.fiafnet.org/pages/E-Resources/LoD-Task-Force-Workshop-2019.html).

You can also search for other LOD vocabulary and authority sources on [BARTOC](http://bartoc.org/), for example those related to "[film](http://bartoc.org/vocabularies?search=film#)".


## What is @id doing?
Linking to external identifiers is at the heart of Linked Data. In JSON-LD, this is often done in the `@id` field. You can see the distinction below:

A LOD resource as value:

```
{
  "landingPage": {
    "@id": "http://www.europeana.eu/portal/record/09102/_CM_0839888.html"
  },
  ...
}

```

A string literal as value:

```
{
  "creator": "Europeana",
   ...
}
```

(source: [Europeana](https://pro.europeana.eu/page/record))

## Schemas and Ontologies in JSON-LD

It's possible to combine fields from different schemas and ontologies using the JSON-LD `@context` part. For example, here we know that fields from Dublin Core and the European Data Model (EDM) will be used to describe our item. Any field prefixed with `dc`, such as `dc:creator`, we know refers for the Dublin Core ontology.
<pre>
{
  <b>"@context"</b>: {
    "edm": "http://www.europeana.eu/schemas/edm/",
    "dc": "http://purl.org/dc/elements/1.1/",
  },
 "@graph": [{
    ...
   <b> "dc:creator": "AMIA Open Source",</b>
    }]
 }
</pre>




## LOD for Media Formats
We noticed that most writing on LOD for film and media focus on title and name authorities. We were curious about the implications for LOD for media formats and compiled the beginning of a list for reference.

### Film
 - **PBCore** provides LOD for gauged film formats in its [instantiationPhysical Film Vocabulary](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/).
     - [[8mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#8mmFilm), [9.5mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#9andaHalfmmFilm), [Super 8mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#Super8mmFilm), [16mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#16mmFilm), [Super 16mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#Super16mmFilm), [22mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#22mmFilm), [28mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#28mmFilm), [35mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#35mmFilm), [70mm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#70mmFilm](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#70mmFilm))]
     
 - **Getty AAT** provides LOD for members of its  \<size for photographic film> [term](http://vocab.getty.edu/aat/300263814):
     - [[8mm](http://vocab.getty.edu/aat/300263859), [16mm](http://vocab.getty.edu/aat/300263815), [Super 16mm](http://vocab.getty.edu/aat/300264669), [35mm](http://vocab.getty.edu/aat/300263816), [65mm](http://vocab.getty.edu/aat/300264670), [70mm](http://vocab.getty.edu/aat/300264672)] 
     
     
 - **Wikidata** has entries for several sizes:
     - [[8mm](https://www.wikidata.org/wiki/Q270183), [16mm](https://www.wikidata.org/wiki/Q194383), [Super 16mm](https://www.wikidata.org/wiki/Q2713357)]

### Video
 - **PBCore** provides LOD for physical video formats in its [instantiationPhysical Video Vocabulary](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/).
   - [[Videocassette](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Videocassette), [Open reel videotape](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#OpenReelVideoTape), [Optical video disc](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#OpticalVideoDisc), [1 inch videotape](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#1InchVideotape), [1/2 inch videotape](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#HalfInchVideotape), [1/4 inch videotape](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#QuarterInchVideotape), [2 inch videotape](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#2InchVideotape), [Betacam](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Betacam), [Betacam SX](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#BetacamSX), [Betamax](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Betamax), [Blu-ray disc](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#BluRayDisc), [Catrivision](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Catrivision), [D1](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D1), [D2](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D2), [D3](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D3), [D5](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D5), [D6](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D6), [D9](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#D9), [DCT](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DCT), [Digital Betacam](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DigitalBetacam), [Digital8](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Digital8), [DV](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DV), [DVCAM](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DVCAM), [DVCPRO](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DVCPRO), [DVD](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#DVD), [EIAJ](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#EIAJ), [EVD](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#EVD), [HDCAM](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#HDCAM), [HDV](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#HDV), [Hi8](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Hi8), [LaserDisc](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#LaserDisc), [MII](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#MII), [MiniDV](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#MiniDV), [Super Video CD](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#SuperVideoCD), [U-matic](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Umatic), [Universal Media Disc](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#UniversalMediaDisc), [V-Cord](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Vcord), [VHS](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#VHS), [Video8](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#Video8), [VX](http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-video-vocabulary/#VX)]

- **Getty AAT** provides LOD, but further research is needed to identify the appropriate Guide Term(s) and Object(s) related to physical video.

- **Wikidata** has entries for several physical video formats and carriers, including:
   - [[Betacam](https://www.wikidata.org/wiki/Q830910), [Digital Betacam](https://www.wikidata.org/wiki/Q1751553), [Betacam SP](https://www.wikidata.org/wiki/Q830904), [videotape](https://www.wikidata.org/wiki/Q747779), [VHS](https://www.wikidata.org/wiki/Q183976), [DVD](https://www.wikidata.org/wiki/Q5294), 
[Laserdisc](https://www.wikidata.org/wiki/Q273309), [open reel videotape](https://www.wikidata.org/wiki/Q29167500), [U-matic](https://www.wikidata.org/wiki/Q278080), [Betamax](https://www.wikidata.org/wiki/Q690148), [Blu-ray Disc](https://www.wikidata.org/wiki/Q47770), [Digital Betacam](https://www.wikidata.org/wiki/Q1751553)
[Digital8](https://www.wikidata.org/wiki/Q930337), [DV](https://www.wikidata.org/wiki/Q3796889), [DVCAM](https://www.wikidata.org/wiki/Q1361160), [HDCAM](https://www.wikidata.org/wiki/Q1194529), [8 mm video format](https://www.wikidata.org/wiki/Q1155472), [MiniDV](https://www.wikidata.org/wiki/Q6957908), [Hi8](https://www.wikidata.org/wiki/Q2302273)]


## Example Record
Here's a kitchen sink example of a JSON-LD record, combining what we've outlined above!

<pre>
{
  "@context": {
    "sch": "https://schema.org/",
    "edm": "http://www.europeana.eu/schemas/edm/",
    "pbc": "http://pbcore.org/pbcore-controlled-vocabularies/",
    "custom": "http://myinstitution.com"
  },
  "@graph": [
    {
      "@id": "https://www.wikidata.org/wiki/Q202548",
      "@type": "sch:Movie",
      "sch:name": "Vertigo",
      "sch:datePublished": "1958",
      "sch:director": {
        "@id": "https://www.wikidata.org/wiki/Q7374"
      },
      "sch:titleEIDR": {
        "@id": "10.5240/39FE-B96B-01BE-453E-64D7-E"
      },
      "sch:sameAs": {
        "@id": "https://www.imdb.com/title/tt0052357"
      },
      "sch:workExample": {
        "@type": "sch:Movie",
        "sch:editEIDR": {
          "@id": "10.5240/BDF9-F812-FC30-3EAF-AEB3-O",
          "sch:disambiguatingDescription": "35mm Theatrical Print"
        },
        "sch:duration": "PT2H8M",
        "pbc:instantiationPhysical": {
          "@id": "http://pbcore.org/pbcore-controlled-vocabularies/instantiationphysical-film-vocabulary/#35mmFilm"
        },
        "custom:gauge": {
          "@id": "https://www.wikidata.org/wiki/Q226528"
        }
      }
    },
    {
      "@id": "http://semium.org/time/1958",
      "@type": "edm:TimeSpan"
    }
  ]
}
</pre>

Explanation of example record coming soon..

## Future Work

We aspire to act in alignment with the [FIAF LOD Task Force](https://www.fiafnet.org/pages/E-Resources/LoD-Task-Force-Workshop-2019.html)'s priorities by lowering the bar to engaging with linked data. With community input, we can put together more resources or tutorials based on need and interest.

A missing resource on the web seems to be example records. We hope to add a number of them above.

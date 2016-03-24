# Software Architecture 2015/2016

:computer: *Faculdade de Ciências da Universidade do Porto* :computer:

![logo](https://picard.musicbrainz.org/static/img/picard-icon-large.svg)

### Group Elements
- Tiago Martins
- Raul Ferreira
- Paula Giesta
- Dinis Costa
- Saúl Costa

### Description
[MusicBrainz Picard] (http://picard.musicbrainz.org) is a software application used to identify, tag and organize locally stored music collections. It is developed mainly by the San Luis Obispo, CA, USA based, tax-exempt and not-for-profit [MetaBrainz Foundation] (https://metabrainz.org). It is also free and open source software (FOSS), written in Python.

The program uses the existing metadata and/or the acoustic fingerprint stored in local music files and compares it to the MusicBrainz database. The database is maintained bay the community, therefore many songs might not yet be in the database, so the mission of tagging the music file is up to the end user. The core data of the database is in the public domain as is released under the CC0 license while accessory/supplementary data is released under the CC BY-NC-SA 3.0 license, while the database itself is written in Perl/PostgreSQL (more information about the database and - if you want, to download it - can be accessed on the [MusicBrainz Database] (http://musicbrainz.org/doc/MusicBrainz_Database) website). Of course, the more informtion the database have about a particular recording, the more information it can display in the music file.

Outside the online functionalities, it is a normal album-oriented tag editor, with support for plugins and personalization, supporting virtually every music file format and its respective metadata container, be it open-source or commercial, be it a physical release or a digital download.

The name chosen for the software is a hommage to Captain Jean-Luc Picard, the main character in the popular 1987-1994 sci-fi series Star Trek: The Next Generation, portrayed by Sir Patrick Stewart, OBE.

### Requirements
#### System Requirements

[MusicBrainz Picard] (http://picard.musicbrainz.org) requires a Linux/Mac OS X/Windows system with network connectivity and also needs Python to be installed.

### Development

There are several components that form **MusicBrainz** and that are necessary for its functioning: the **MusicBrainz Server**, **MusicBrainz Database**, **web service** and related **client libraries**, and applications/services. 

The [MusicBrainz Server] (https://musicbrainz.org/doc/MusicBrainz_Server) is written in Perl and is an open source software application that provides the primary interface to the [MusicBrainz Database] (https://musicbrainz.org/doc/MusicBrainz_Database). Users can edit the data on the website, and the web service power client applications like MusicBrainz Picard.

The MusicBrainz Database contains all the music metadata (that includes information about artists, recordings, releases, works and labels), and is built on the PostgreSQL relational database engine. The full history of all the changes that the MusicBrainz community has made is also stored in this database. 

The development of [Picard](http://picard.musicbrainz.org) started in 2003, and the development of its recent structure started in 2007. The developer community is mostly situated in North America and Europe.

### Issues

This Project does not use the Github [Issues](https://github.com/features#issues) functionality, instead Musicbrainz uses it's own [bug tracker](http://tickets.musicbrainz.org/) which uses the software [JIRA Software](https://www.atlassian.com/software/jira)

Aside from collecting bugs to fix, the developers seem to use the Issues infrastructure as a way to track which feautures will be implemented next and by whom. They tag those new feature with the particular version that should have them implemented.

![](issues-history.PNG)

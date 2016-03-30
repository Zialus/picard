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

The program uses the existing metadata and/or the acoustic fingerprint stored in local music files and compares it to the MusicBrainz database. The database is maintained by the community, therefore many songs might not yet be in the database, so the mission of tagging the music file is up to the end user. Of course, the more information the database has about a particular recording, the more information it can display in the music file.

Outside the online functionalities, it is a normal album-oriented tag editor, with support for various plugins and services, supporting virtually every music file format and its respective metadata container, be it open-source or commercial, lossy or lossless, physical release or digital download.

The name chosen for the software is a homage to Captain Jean-Luc Picard, the main character in the popular 1987-1994 sci-fi series Star Trek: The Next Generation, portrayed by Sir Patrick Stewart, OBE.


### Requirements

#### Functional Requirements (Features)

**Clustering** : 
Picard reads and process the metadata from the files. Pressing the "Cluster" button allows to group the files into album clusters. The "Unmatched files" folder stores the files that are not matched into album clusters.

**Lookup and querying MusicBrainz** : 
The lookup can be automatic or manual. By using the "Lookup" button in the toolbar, Picard will query MusicBrainz and attempt to find the best match to the user´s cluster or file. The alternative is to manually lookup. Also, if the user select a set of files and click "Scan", Picard will find AcoustIDs based on audio fingerprint for the files, and query MusicBrainz to find a track that matches them. 

**Saving** : 
After matching up files to albums, users can click the "Save" button to save that track/album. 

Additionally, Picard can be customized using scripts and plugins (i.e. customize how to apply the MusicBrainz metadata to files, encapsulate scripting, download cover art, and add other functionalities to Picard).

 **Supported file formats and respective metadata container**
 
|File Format|Metadata Container|
|:---------:|:----------------:|
|AAC        |iTunes MP4|
|Apple Lossless|iTunes MP4|
|FLAC       |Vorbis Comment|
|Monkey's Audio|APEv2 Tag|
|MP3        |ID3|
|Musepack   |APEv2 Tag|
|Ogg Vorbis |Vorbis Comment|
|OptimFROG  |APEv2 Tag|
|Opus       |Vorbis Comment|
|Speex      |Vorbis Comment|
|TTA        |ID3|
|WAV        |N/A|
|WavPack    |APEv2 Tag|
|WMA        |ASF|

#### Non-Functional Requirements

**System Requirements** : MusicBrainz Picard requires a Linux/Mac OS, X/Windows system with network connectivity and also needs Python to be installed.

---
**TO-DO!!!!!!!!!!!!!!!!!**

- Maintainability
- usability
- accessibility 
- ... 

---



### Development

There are several components that form MusicBrainz and that are necessary for its functioning: the **MusicBrainz Server**, **MusicBrainz Database**, **web service** and related **client libraries**, and applications/services. 

The [MusicBrainz Server] (https://musicbrainz.org/doc/MusicBrainz_Server) is written in Perl and is an open source software application that provides the primary interface to the [MusicBrainz Database] (https://musicbrainz.org/doc/MusicBrainz_Database). Users can edit the data on the website, and the web service power client applications like MusicBrainz Picard.

The MusicBrainz Database contains all the music metadata (that includes information about artists, recordings, releases, works and labels), and is built on the PostgreSQL relational database engine and is written in Perl. The full history of all the changes that the MusicBrainz community has made is also stored in this database. The core data of the database is in the public domain as is released under the CC0 license while accessory/supplementary data is released under the CC BY-NC-SA 3.0 license (more information about the database and - if you want, to download it - can be accessed on the [MusicBrainz Database] (http://musicbrainz.org/doc/MusicBrainz_Database) website).

The development of [Picard](http://picard.musicbrainz.org) started in 2003, and the development of its recent structure started in 2007. The developer community is mostly situated in North America and Europe.

### Commits

#### Contributors and commit frequency

Since its start, this project has had 40 contributors and a total of 3619 commits. There are 4 main contributors with more than 100,000 modifications each and these are the ones who had the biggest influence in the project, several others with more than 1,000 modifications each, that made small changes, but the majority of contributors have just submitted small bug fixes.

After analysing the number of commits over the years, we can conclude the most active phases and the current state of the project.
The largest number of commits happened between 30th March 2013 and 20th December 2014, with 1340 commits, corresponding to release 1.3.1. The most inactive years of this project are 2010, with only 52 commits (8350 lines added and 7719 lines removed), and the current year (until 30th March), with only 29 commits (289 lines added and 175 lines removed).

The following table shows the number of commits over the years (including the percentage of all commits), and the releases of each of those years.

   Year       | Number of commits in period | Total number of commits | Releases
------------- | --------------------------- | ----------------------- | --------
2016          | 29 (0.80%)                  | 3619                    | 
2015          | 227 (6.27%)                 | 3590                    | <li>release-1.3.2 (06-01-2015)</li>
2014          | 955 (26.39%)                | 3363                    | <li>release-1.3.1 (20-12-2014)</li><li>release-1.3 (20-10-2014)</li>
2013          | 492 (13.59%)                | 2408                    | <li>release-1.2 (30-03-2013)</li>
2012          | 344 (9.51%)                 | 1916                    | <li>release-1.1 (03-09-2012)</li><li>release-1.0 (02-06-2012)</li>
2011          | 387 (10.69%)                | 1572                    | <li>release-0.16 (23-10-2011)</li><li>release-0.15.1 (31-07-2011)</li><li>release-0.15 (17-07-2011)</li><li>release-0.14 (15-05-2011)</li><li>release-0.13 (06-03-2011)</li>
2010          | 52 (1.44%)                  | 1185                    |
2009          | 203 (5.61%)                 | 1133                    | <li>release-0.12.1 (01-11-2009)</li><li>release-0.12 (25-10-2009)</li>
2008          | 178 (4.92%)                 | 930                     | <li>release-0.11 (01-12-2008)</li><li>release-0.10 (27-07-2008)</li>
2007          | 451 (12.46%)                | 752                     | <li>release-0.9.0 (16-12-2007)</li>
2006          | 301 (8.32%)                 | 301                     |

The top contributor to the project has changed over the years as shown in the following table:

   Year       | Author                      | Commits (%)
------------- | --------------------------- | -----------
2016          | Laurent Monin               | 13 (44.83% of 29)
2015          | Laurent Monin               | 137 (60.35% of 227)
2014          | Laurent Monin               | 569 (59.58% of 955)
2013          | Laurent Monin               | 179 (36.38% of 492)
2012          | Michael Wiencek	            | 125 (36.34% of 344)
2011          | Michael Wiencek	            | 184 (47.55% of 387)
2010          | Philipp Wolfer              | 48 (92.31% of 52)
2009          | Philipp Wolfer              | 124 (61.08% of 203)
2008          | Philipp Wolfer              | 84 (47.19% of 178)	
2007          | Lukáš Lalinský              | 439 (97.34% of 451)
2006          | Lukáš Lalinský              | 300 (99.67% of 301)	


### Issues

This Project does not use the Github [Issues](https://github.com/features#issues) functionality, instead Musicbrainz uses it's own [bug tracker](http://tickets.musicbrainz.org/) which uses the software [JIRA Software](https://www.atlassian.com/software/jira)

Aside from collecting information about bugs (which can then be assigned to a particular developer to fix), the developers seem to use the Issues infrastructure as a way to track which features will be implemented next and by whom. They make use of a tagging system to indicate by which version that a specific feature needs to be implemented.

Overall the issue tracker seems to be the central place to track the progress of this project. 

As the picture below shows the team is reasonably quick to address the created issues.

![](issues-history.PNG)

### Continuous Integration

Until [2013] (https://oxygene.sk/2013/12/daily-picard-builds-for-windows/) there wasn't any kind of automation behind the build process. At that point [Jenkins](https://jenkins.io/) was chosen as a tool to automate the testing of builds for [Windows](http://build.oxygene.sk/job/package-picard-win-daily/
), and later on for [OS X](http://build.oxygene.sk/job/package-picard-osx-daily/
)

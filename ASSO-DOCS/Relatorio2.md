# Software Architecture 2015/2016

:computer: *Faculdade de Ciências da Universidade do Porto* :computer:

![logo](https://picard.musicbrainz.org/static/img/picard-icon-large.svg)

### Group Elements

-   Dinis Costa
-   Paula Giesta
-   Raul Ferreira
-   Tiago Martins
-   Saúl Costa

#### Logical View

![](logicalView.png)

After analysing the project structure, we have chosen to represent the Logical view using a class diagram.
Given the project complexity, we chose not to show all classes and to consider the most important only.

The project has a main class "Tagger" which is composed by the following classes:
- **PluginManager**, which manages the plugins installed on the system.
- **XmlWebService**, which is responsible for linking to the "Metabrainz" server.
- **MainWindow**, which manages the graphical interface, and is composed by the classes:
  - **FileBrowser**, that allows to work with local files / browse the file system,
  - **MetadataBox**, that is responsible for presenting the detailed information of each file, also allowing user input to change the metadata,

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
  - **MainPanel**, which corresponds to the main display area and program interaction.


- **Cluster**, that allows to group the files into clusters (e.g. arrange tracks into albums).

The "Item" class is a generalization of the classes "Cluster", "Album", "File" and "Track".
The "File" class is composed by "Metadata", as well as the "Album" class, which is also composed by "Cluster".
The "DataObject" class is a generalization of "Album" and "Track".
The "LockableObject" is a generalization of the "DataObject" and "Config.Section", which in turn is composed by "Config" (that sets the configurations, e.g. sets current profile and upgrade configuration version to the latest).

# ColorXml QuickLook v1.2
### Freeware by CED Lecca 2007-2009 (Minor updates by Aubin Paul in 2018)

This is a simple QuickLook plugin which enables to display XML files with indentation and XML syntax coloring.

Usage:

1. Drag the `colorxml.qlgenerator` file to `/Library/QuickLook`
2. Reboot or logout or execute the command `qlmanage -r` from the Terminal
3. Enjoy quicklook on XML Files!

Note: includes the following xsl stylesheet to generate an HTML version of the XML file:

[xmlverbatim by Oliver Becker](http://www2.informatik.hu-berlin.de/~obecker/XSLT/#xmlverbatim)

Advanced users note: It works by transforming the XML in an HTML file, it is possible to change the styles used in the display by modifying the file `colorxml.qlgenerator/Contents/Resources/xmlverbatimwrapper.xsl` in the package.

The program now handles the following XML-based file types:

- XML
- XSL thanks to Simone
- XSD thanks to Alan Pagliere
- RSS
- GXL thanks to Nicolas Sidere
- plist thanks to Stephan Ruggiero
- MXML thanks to Pedro Jimenez

## Adding new XML-based Types

- Open the Terminal
- execute the command

`qlmanage -d 4 -t  <filename>`

- the output will include a line like this:

`[DEBUG] Thumbnailing /usr/share/texinfo/texinfo.xsl - type: dyn.xxxxxx -`

- write down the Content UTI Type (`dyn.xxxxxx`)

- backup the file `/Library/QuickLook/colorxml.qlgenerator/Contents/Info.plist`  in a safe place

- edit the file `/Library/QuickLook/colorxml.qlgenerator/Contents/Info.plist` 

- add the new Content Type UTI in the XML file in the list:

```xml
<array>
 <string>public.xml</string>
 <string>public.xsd</string>
 <string>dyn.ah62d4rv4ge81u65q</string>
        ...
</array>
```
- execute the command qlmanage -r to reset quicklook
- go to the Finder and check if the preview works.. if it doesn't work, restore the `Info.plist` from the backup and execute `qlmanage -r` again




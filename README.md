# Calibre OPDS Client

[![build](https://github.com/goodlibs/calibre-opds-client/workflows/build/badge.svg)](https://github.com/goodlibs/calibre-opds-client/actions?query=workflow%3Abuild)  [![Code Style: Black](https://img.shields.io/badge/code_style-black-000000.svg)](https://github.com/python/black)

Download books from an OPDS catalog using a Calibre plugin.

## :books: Background

[Calibre](https://calibre-ebook.com) is a cross-platform open-source suite of e-book software.
Calibre supports organizing existing e-books into virtual libraries, displaying, editing, creating and converting e-books, as well as syncing e-books with a variety of e-readers.

The [Open Publication Distribution System](https://en.wikipedia.org/wiki/Open_Publication_Distribution_System) (OPDS) catalog format is a syndication format for electronic publications based on Atom and HTTP.
OPDS catalogs enable the aggregation, distribution, discovery, and acquisition of electronic publications.

The **Calibre OPDS Client** is a Calibre plugin that reads from an OPDS server and downloads the contents to a Calibre library.

## :hammer_and_wrench: Installation

1. Ensure [Calibre](https://calibre-ebook.com/download) is installed on your machine and the [command line tools](https://manual.calibre-ebook.com/generated/en/cli-index.html) are available in your search path.

1. Install the plugin.
    ```bash
    cd calibre_plugin
    calibre-customize -b .
    ```

1. Restart Calibre.

1. Add the plugin to the main toolbar.
    1. Open the Preferences menu.
    1. Under the `Interface` section, click on the button labeled `Toolbars & menus`.
    1. Click the dropdown menu and select `The main toolbar`.
    1. Select `OPDS Client` under `Available actions` on the left side.
    1. Click the right arrow (`>`) to add it to the main toolbar.
    1. Click `Apply`, then `Close` the Preferences menu.

## :computer: Usage

### Download books from an external OPDS catalog

```
https://standardebooks.org/opds
```

### Replicate a book collection between two computers on a LAN

1.  In the calibre you wish to copy from (in this example called
    calibre1.home.lan):
    1.  Click Preferences
    2.  In the "calibre - Preferences" dialog:
        1.  Click "Sharing over the net"
        2.  In the "calibre - Preferences - Sharing over the net"
            dialog:
            1.  Click the "Start Server" button
            2.  Select the checkbox "Run server automatically when
                calibre starts"
            3.  Click the "Apply" button
        3.  Click the "close" button
2.  In the calibre you wish to copy to
    1.  Install this plugin (see the "How do I install it?" section)
    2.  Click the "OPDS client" button
    3.  In the "OPDS client" dialog
        1.  Edit the "OPDS URL" value, change
            
            ``` example
            http://localhost:8080/opds
            ```
            
            to
            
            ``` example
            http://calibre1.home.lan:8080/opds
            ```
            
            and then press the RETURN key on the keyboard
        
        2.  Click the "Download OPDS" button
        
        3.  Wait until the OPDS feed has finished loading (this may take
            some time if there is a large number of books to load)
            
              - Note: if no books appear, try unchecking the "Hide books
                already in the library" checkbox. If that makes a lot of
                books appear, it means that the two calibre instances
                have the same books
        
        4.  select the books you wish to copy into the current calibre
            and click the "Download selected books"
            
              - calibre will start downloading and installing the books:
                  - The Jobs counter in calibre's lower right corner,
                    will show a decrementing number and the icon will
                    spin
                  - The book list will be updated as the books are
                    downloaded
        
        5.  The downloaded books will be in approximately the same order
            as in the original, but the time stamp will be the download
            time. To fix the time stamp, click on the "Fix timestamps of
            the selection" button
            
              - The updated timestamps may not show up immediately, but
                they will show up after the first update of the display,
                and the books will be ordered according to the timestamp
                after stopping and starting calibre

## :balance_scale: License

This code is licensed under the GNU General Public License v3.0.
For more details, please take a look at the [LICENSE](https://github.com/goodlibs/calibre-opds-client/blob/master/LICENSE) file.

## :handshake: Contributing

Contributions are welcome!
Please feel free to open an issue or submit a pull request.

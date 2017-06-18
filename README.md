# SheetFeed

SheetFeed.php is a simple, poorly written, Google Sheets to ATOM (RSS) feed generator. It leans heavily on a number of real, high quality projects.

SheetFeed was developed primarily for use with the [RiseVision](https://www.risevision.com/) RSS feed display plugin for their digital signage product, but may be of use to anyone who needs to create super simple ATOM (RSS) feeds. It is NOT suitable for containerised feeds such as podcasts, sorry.

## Getting Started

SheetFeed requires a couple of dependent open source PHP projects as a writable cache directory on your web server. You will, of course, need a Google Sheet to publish from.

I have included the versions of the dependencies I developed against in the repo, I STRONGLY suggest you get the latest versions from the links below.

### Prerequisites

You will need:
1. A web server with PHP
2. A directory on that web server
3. A web server writable 'cache' directory
4. A copy of [PhpSpreadsheet](https://github.com/PHPOffice/PhpSpreadsheet)
5. A copy of [FeedWriter](https://github.com/mibe/FeedWriter)

### Installing

To get it up and running:
1. Create a directory on an existing website, or create a website for this purpose
2. Create a web server writable 'cache' directory
3. Download SheetFeed.php and place it in the web root for this project
4. You may like to do some .htaccess trickery or rename SheetFeed.php to something useful
5. Download [PhpSpreadsheet](https://github.com/PHPOffice/PhpSpreadsheet) and place an unmodified copy in the web root for this project
6. Download [FeedWriter](https://github.com/mibe/FeedWriter) and place an unmodified copy in the web root for this project
7. Edit SheetFeed.php and set the config[] array variables for your project

### Your Google Sheet

The Google Sheet you wish to use must be published to the web as an .XLSX file. When you have done this, Google will provide you a URL with a reference string in the format https://docs.google.com/spreadsheets/d/REFERENCE-STRING-IS-HERE/pub?output=xlsx . You will need this string.

SheetFeed.php uses simple query string parameters to define behaviour and on the fly configuration. The most simple example would be to open a web browser (or RSS reader, but lets start easy) and browse to http://your.url/SheetFeed.php?google=REFERNCE-STRING&sheet=SHEET-NAME .

To get a bit tricker, here are the accepted parameters, and their (default values). All sheet names are URL encoded.
* &google= google spreadsheet reference
* &sheet= sheet name
* &title= column of post title (A)
* &content= column of post content (B)
* &start= column of date to start posting (C)
* &end= column of date to stop posting (D)
* &author= column of post author (E)
* &end= column of date to stop posting (F)
* &header= row of header cells to ignore, set 0 for no header (1)


## Contributing

If you think you can make an improvement to SheetFeed.php, which is highly likely, simple submit a pull request on this repo.

## Authors

* **Ryan Lovett** - [ryanlovett-au](https://github.com/ryanlovett-au)

## License

This project is licensed under the GPLv3 License - see the [GPL Website](https://www.gnu.org/licenses/gpl-3.0.en.html) for details
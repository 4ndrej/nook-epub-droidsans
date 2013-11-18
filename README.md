## Nook EPUB Droidsans

This is a simple Python script for injecting a CSS stylesheet into an EPUB file that
will force the reader to render using the `Arial` font stored on `/system/media/sdcard/fonts/`.

### Motivation

On [first generation Nook](http://www.barnesandnoble.com/u/Support-NOOK-1st-Edition/379003191),
non-English characters such as non-latin1 characters are not displayed correctly without the
correct font.

The [existing method](http://www.cnepub.com/discuz/forum.php?mod=viewthread&tid=21195&page=1&authorid=144624)
is to add additional CSS declaractions into the EPUB by using Calibre.

As I do not use Calibre for managing my eBooks, I changed [Victor Neo's](https://github.com/victorneo) [nook-epub-droidsans](https://github.com/victorneo/nook-epub-droidsans) script to
create a CSS file and add the `<link>` tag to all HTML files within the EPUB file.

The CSS is based on styleshhet from [Font Changes](http://nookdevs.com/Font_Changes#Instructions_for_Linking_3rd_Party_Fonts_from_ePubs) page.

### Usage

    python convert.py [epub file name]

    eg. python convert.py my_book.epub
    An EPUB file named my_book_nook.epub will be generated.
    The original EPUB file is left untouched.

### Caveats

The script assumes that your EPUB file does not contain DRM. It also assumes that the sdcard contains `fonts` folder with `arial.ttf, arialbd.ttf, ariali.ttf and arialbi.ttf` files.

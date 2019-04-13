# jsPDF

[![Greenkeeper badge](https://badges.greenkeeper.io/MrRio/jsPDF.svg)](https://greenkeeper.io/)
[![Build Status](https://saucelabs.com/buildstatus/jspdf)](https://saucelabs.com/beta/builds/526e7fda50bd4f97a854bf10f280305d)
[![Code Climate](https://codeclimate.com/repos/57f943855cdc43705e00592f/badges/2665cddeba042dc5191f/gpa.svg)](https://codeclimate.com/repos/57f943855cdc43705e00592f/feed)
[![Test Coverage](https://codeclimate.com/repos/57f943855cdc43705e00592f/badges/2665cddeba042dc5191f/coverage.svg)](https://codeclimate.com/repos/57f943855cdc43705e00592f/coverage)
[![GitHub license](https://img.shields.io/github/license/MrRio/jsPDF.svg)](https://github.com/MrRio/jsPDF/blob/master/LICENSE)



**A library to generate PDFs in JavaScript.**

You can [catch me on twitter](http://twitter.com/MrRio): [@MrRio](http://twitter.com/MrRio) or head over to [my company's website](http://parall.ax) for consultancy.

## [Live Demo](http://raw.githack.com/MrRio/jsPDF/master/docs/) | [Documentation](http://raw.githack.com/MrRio/jsPDF/master/docs/)

## Creating your first document

The easiest way to get started is to drop the CDN hosted library into your page:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/1.5.3/jspdf.debug.js" integrity="sha384-NaWTHo/8YCBYJ59830LTz/P4aQZK1sS0SneOgAvhsIl3zBu8r9RevNg5lHCHAuQ/" crossorigin="anonymous"></script>
```

Integrity-hash generated by https://www.srihash.org/

or can always get latest version via [unpkg](https://unpkg.com/#/)

```html
<script src="https://unpkg.com/jspdf@latest/dist/jspdf.min.js"></script>
```

Using yarn:

```bash
yarn add jspdf
```

Using npm:

```bash
npm install jspdf --save
```

Then you're ready to start making your document:

```javascript
// Default export is a4 paper, portrait, using milimeters for units
var doc = new jsPDF()

doc.text('Hello world!', 10, 10)
doc.save('a4.pdf')
```

If you want to change the paper size, orientation, or units, you can do:

```javascript
// Landscape export, 2×4 inches
var doc = new jsPDF({
  orientation: 'landscape',
  unit: 'in',
  format: [4, 2]
})

doc.text('Hello world!', 1, 1)
doc.save('two-by-four.pdf')

```

## Use of UTF-8 / TTF:

The 14 standard fonts in PDF are limited to the ASCII-codepage. If you want to use UTF-8 you have to to integrate a custom font, which provides the needed glyphs. jsPDF supports .ttf-files. So if you want to have for example chinese text in your pdf, your font has to have the necessary chinese glyphs. So check if your font supports the wanted glyphs or else it will show a blank space instead of the text.

To add the font to jsPDF use our fontconverter in [/fontconverter/fontconverter.html](https://rawgit.com/MrRio/jsPDF/master/fontconverter/fontconverter.html) . The fontconverter will create a js-file with the content of the provided ttf-file as base64 encoded string and additional code for jsPDF. You just have to add this generated js-File to your project. You are then ready to go to use setFont-method in your code and write your UTF-8 encoded text.

## Angular/Webpack/React/etc. Configuration:

If you are using Webpack (including managed cli tools like angular-cli or create-react-app) you can import like this:

```
import * as jsPDF from 'jspdf'
```

In some frameworks you have to import jsPDF like this:

```
import jsPDF from 'jspdf';
```

You can add jsPDF to your meteor-project as follows:

```
meteor add jspdf:core
```

## Support

Please check if your question is already handled at Stackoverflow <https://stackoverflow.com/questions/tagged/jspdf>.
Feel free to ask a question there with the tag `jspdf`.

Feature requests, bug reports etc. are very welcome as issues. Note that bug reports should follow these guidelines:

* A bug should be reported as an [mcve](https://stackoverflow.com/help/mcve)
* Make sure code is properly indented and [formatted](https://help.github.com/articles/basic-writing-and-formatting-syntax/#quoting-code) (Use ``` around code blocks)
* Provide a runnable example.
* Try to make sure and show in your issue that the issue is actually related to jspdf and not your framework of choice your setup.

## Contributing

Build the library with `npm run build`. This will fetch all dependencies and then compile the `dist` files. To see the examples locally you can start a web server with `npm start` and go to `localhost:8000`.

Alternatively, you can build jsPDF using these commands in a readily configured online workspace:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#https://github.com/MrRio/jsPDF)

## Credits
- Big thanks to Daniel Dotsenko from [Willow Systems Corporation](https://github.com/willowsystems) for making huge contributions to the codebase.
- Thanks to Ajaxian.com for [featuring us back in 2009](http://ajaxian.com/archives/dynamically-generic-pdfs-with-javascript).
- Our special thanks to GH Lee ([sphilee](https://github.com/sphilee)) for programming the ttf-file-support and providing a large and long sought after feature
- Everyone else that's contributed patches or bug reports. You rock.

## License (MIT)
Copyright (c) 2010-2017 James Hall, https://github.com/MrRio/jsPDF

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

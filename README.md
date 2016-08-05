# Fastatic
> Speed up your static site with one command

## Usage

### CLI

```bash
$ fastatic my-static-site/
```

```bash
$ fastatic my-static-site-source/ --dest my-static-site/
```

### JS

```javascript
const fastatic = require('fastatic');
fastatic();
```

#### Configure patterns

```javascript
// configure patterns:
fastatic({
    js: {
      pattern: ['**/*.js', '!**/*.min.js'],
    }
});
```

#### Disable a parser

```javascript
// Disable a parser:
fastatic({
    js: false
});
```

## Default parsers

parser | pattern | function
--- | --- | ---
`css` | `**/*.css` | Minify stylesheets
`js` | `**/*.js` | Minify javascript files
`json` | `**/*.json` | Minify json files by removing all whitespace 
`html` | `**/*.html` | Minify HTML by removing whitespace and minifying inline css/javascript
`images` | `**/*.{gif,jpg,jpeg,png,svg}` | Optimize images and SVG files
`xml` | `**/*.xml` | Minify XML files by removing all whitespace and comments


## Known limitations

* *Fastastic* doesn't concatenate files (css / js ) because there is no reliable way to determine the combinations in which these files are served, nor does it know about the protocol over which it's served (HTTP/1 or HTTP/2).
* *Fastastic* doesn't resize images (png / jpg / gif) because there is no reliable way to determine which sizes the images are displayed in.


## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for [guidelines](CONTRIBUTING.md#guidelines) and [development scripts](CONTRIBUTING.md#scripts).


## License

[MIT licensed](LICENSE) © [De Voorhoede](https://www.voorhoede.nl/)

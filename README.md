# MOK Project - Multilingual Onscreen Keyboard

### We Are Now Serving From A CDN!

#### You can now easily include this plugin right in your project without the need to have any code locally.

Latest Version
```sh
<script src="https://cdn.jsdelivr.net/npm/mok-project@latest/dist/main.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/mok-project@latest/dist/styles.css">
```

Current Version
```sh
<script src="https://cdn.jsdelivr.net/npm/mok-project@1.1.5/dist/main.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/mok-project@1.1.5/dist/styles.css">
```

_If no local languages file is found, the keyboard will pull languages from the CDN._

<br>

The goal of this project is to materialize a well-styled, onscreen keyboard capable of supporting numerous languages fed from .klc files generated by Microsoft Keyboard Layout Creator. This has proven to be the most-reliable source of unicode data along with dead keys and ligature support but I am willing to make revisions if a better source is found. Typical use cases for this application include terminals, kiosks, and other touch-point devices. I hope to provide the community with a valuable resource that only grows better with time and your support!

[Super Basic Demo](http://www.seanmcquay.com/mok-project/sample-keyboard.htm)

Current work is underway to develop a variant of the keyboard which is not only condensed in layout but also allows for the keyboard to be appended near the selected input element to facilitate direct entry into the selected field instead of using a modal and dedicated entry field. _(28 June 2017)_

## Usage

To initiate an instance of the keyboard within your application you may include the following script:

```sh
<script src="https://cdn.jsdelivr.net/npm/mok-project@latest/dist/main.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdn.jsdelivr.net/npm/mok-project@latest/dist/styles.css">

<script type="text/javascript">
    $(document).ready(function() {
        $(document).keyboard({
            language: 'us',
            keyboardPosition: 'bottom'
        });
    });
</script>
```

#### Serving Languages

The keyboard will first search for the given language file in `./languages/` and if not found, will pull from the CDN.

## Installation / Running

This project is built with Gulp which sits atop NodeJS.

Install [Node.js](https://nodejs.org/en/download/)

Update npm to the latest version and install dependencies.

```sh
$ npm install npm@latest -g
$ npm install
$ npm install gulp-cli -g
```

To enter develop mode and launch a server:

```sh
$ gulp develop
```

To issue a new build:

```sh
$ gulp build
```

Source maps may also be generated by appending the flag:

```sh
$ gulp develop --sourcemaps
```

#### Prerequisites / Dependencies

This project was built and tested on jQuery 3.2 and is fed .klc files from [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) V1.4.

#### Options

| Option | Default Value | Information |
|--------|---------------|-------------|
| acceptColor | '#2ECC71' | Defines background color of accept button. May pass hex string or specific color i.e. 'blue'. |
| acceptTextColor | '#FFFFFF' | Defines text color of accept button. May pass hex string or specific color i.e. 'white'. |
| allowEnterAccept | true | Accept keyboard input with hardware keyboard [Enter] key. |
| allowEscapeCancel | true | Cancel keyboard input with hardware keyboard [Escape] key. |
| blackoutColor | '25, 25, 25, 0.9' | Defines color and opacity of blackout background. Passed as RGBA string. |
| cancelColor | '#E74C3C' | Defines background color of cancel button. May pass hex string or specific color i.e. 'blue'. |
| cancelTextColor | '#FFFFFF' | Defines text color of cancel button. May pass hex string or specific color i.e. 'white'. |
| inputFieldRegex | { number: /^(-)?(((&#92;d+)&#124;(&#92;d+&#92;.(&#92;d+)?)&#124;(&#92;.(&#92;d+)?))([eE]([-+])?(&#92;d+)?)?)?$/ } | Define regular expressions for the accepted patterns of input field types. These patterns serve to further restrict browser-specific prepopulated patterns. For example, you may NOT generate a regex to allow letters in an input[type="number"]. Ensure these are whole pattern matches handled by the prepension and appension of ^ and $. The object keys must match identically to the input type. |
| inputType | 'text, textarea, number, password, search, tel, url, contenteditable' | May pass individual input types or comma-separated values. |
| keyCharacterRegex | { number: /[0-9]&#124;[eE]&#124;&#92;.&#124;&#92;+&#124;&#92;-/, tel: /[0-9]&#124;&#92;.&#124;&#92;+&#124;&#92;-&#124;&#92;#&#124;&#92;(&#124;&#92;)/ } | Define regular expressions for input field types. These pertain to the individual key pressed, not the whole accepted pattern. The object keys must match identically to the input type. |
| keyColor | '#E0E0E0' | Defines background color of keys. May pass hex string or specific color i.e. 'blue'. |
| keyTextColor | '#555555' | Defines text color used on keys. May pass hex string or specific color i.e. 'blue'. |
| keyboardPosition | 'bottom' | Locate the keyboard at page 'top', 'middle', or 'bottom' with a default edge padding of 20px. |
| language | none | Given as a string with comma-separated values i.e. 'us, spanish, arabic, russian'. These names correspond to the system file name. If you would like to display a custom language name on the language toggle key, you may enter the language such as 'arabic:العَرَبِيَّة'. Note, you must enable `showSelectedLanguage: true`. |
| languageKeyTextColor | #3498db | Defines text color of language button. May pass hex string or specific color i.e. 'white'. |
| showSelectedLanguage | false | This option labels the language button with the currently-selected language. The name is derived from the actual language file name by default. If you would like to display a custom language name you may map the language such as 'arabic:العَرَبِيَّة'. |
| specifiedFieldsOnly | false | If this option is set to true, the keyboard will only be triggered for those fields which carry: `data-trigger-keyboard="true"` as an HTML attribute. |


#### Callbacks

| Name | Information |
|------|-------------|
| altKey | Define action of [Alt] key |
| ctrlKey | Define action of [Ctrl] key |
| enterKey | Define action of [Enter] key |
| languageKey | Define action of [Language] key |
| spareKey | Define action of [Spare] key |
| tabKey | Define action of [Tab] key |

_You may change the user-displayed names of any keys in keyboard.js without affecting functionality._

## Supported Keyboards

* Albanian
* Arabic
* Azeri-Cyrillic
* Azeri-Latin
* Bashkir
* Belarusian
* Belgian
* Bengali
* Bosnian
* Bulgarian
* Croatian
* Czech-Programmer
* Czech
* Danish
* Dutch
* Estonian
* Faeroese
* Finnish-Sami
* Finnish
* French
* Gaelic
* Georgian
* German
* Greek
* Greenlandic
* Gujarati
* Hausa
* Hebrew
* Hindi
* Hungarian
* Icelandic
* Igbo
* Irish
* Italian
* Japanese-Latin
* Kannada
* Kazakh
* Khmer
* Korean-Latin
* Kyrgyz
* Languages
* Lao
* Latvian
* Lithuanian
* Macedonian
* Malayalam
* Maltese
* Maori
* Marathi
* Mongolian
* Nepali
* Norwegian
* Oriya
* Pashto
* Persian
* Polish
* Portguese-Brazil
* Portguese
* Punjabi
* Romanian
* Russian
* Serbian
* Sesotho-Sa-Leboa
* Setswana
* Sinhala
* Slovak
* Slovenian
* Sorbian
* Spanish
* Swedish
* Swiss-French
* Swiss-German
* Syriac
* Tajik
* Tamil
* Tatar
* Telugu
* Thai-Kedmanee
* Thai-Pattachote
* Tibetan
* Turkish-F
* Turkish-Q
* Turkmen
* Uk
* Ukranian
* Urdu
* US-Dvorak
* US
* Uyghur
* Uzbek
* Vietnamese
* Wolof
* Yakut
* Yoruba

## Customization

If you find that a key position is not where you prefer or you'd like to add additional functionality, you may simply modify the .klc file of your choosing or replicate it as your own version. Depending on the language selected, there may be three different tables you can modify. These include **LAYOUT** which contains standard keys, **DEADKEYS** which contains combinations such as ```a + ` = à```, and **LIGATURE** which contains specific character combinations such as ```a + e = æ```. Standard keys may be modified, starting in column 4. Modifying anything prior to this will cause issues with the way information is parsed from the file. To eliminate a specific character, replace the unicode value with ```-1```. Keys with ```@``` indicate a dead key combination is possible. You may append this symbol to the end of a unicode value and add an entry in the **DEADKEY** table. Columns containing ```%%``` indicate that key ligature occurs i.e. several unicode values are combined to form that key. These may also be revised by modifying / adding entries in the **LIGATURE** table.

For example, you might have the following line:

| SC | VC | Cap | 0 | 1 | 2 | 6 | |
|----|----|-----|---|---|---|---|-|
| 04 | 3 | 0 | 3 | 0023 | -1 | 00a3 | // DIGIT THREE, NUMBER SIGN, <none>, POUND SIGN |

You decide for some reason you'd like to replace the NUMBER SIGN with EXCLAMATION MARK so you might modify the table as such:

| SC | VC | Cap | 0 | 1 | 2 | 6 | |
|----|----|-----|---|---|---|---|-|
| 04 | 3 | 0 | 3 | **0021** | -1 | 00a3 | // DIGIT THREE, EXCLAMATION MARK, <none>, POUND SIGN |

It should be noted that anything after ```//``` is for your own reference and is not used in code.

## Bugs / Drawbacks

##### Ligature
I'm not certain if ligature support is fully functioning for keyboards such as Hindi, Punjabi, Arabic, etc... I need your help in verifying these layouts! I do not speak these languages and I've found keyboard layouts very inconsistent. If you find a keyboard that is not functioning, I'll be happy to make any revisions needed.

##### Testing
I have not personally tested every keyboard and you may find bugs along your journey. I'll work to quickly resolve any issues you might uncover.

##### Mobile Support
This initial release is not intended to be mobile friendly. It's original scope was intended for those devices such as terminals and kiosks. It is the intention to provide mobile support at a later time.

##### Front End File Handling
Due to the nature of JavaScript / jQuery, I currently do not know of a way to load all keyboard layouts in a directory. You must declare all keyboards which you wish to use.

##### Conteneditable
I have not spent much time investigating how nested markup within contenteditable elements will effect the keyboard. I'm not sure the use case and therefore have not pursued this.

##### Pattern Honoring
At a future point, I'd like to support honoring of input patterns. These patterns are typically evaluated on form submission, but I'd like to eventually support them prior to this point.

## Coming Features

* Mobile Support
* Direct Entry (No Modal)
* Condensed Keyboard Layout
* Hardware-Keyboard Mapping (Perhaps)
* Number Pad Only Option
* Keyboard Layout Creator GUI

## Versioning

We use [SemVer](http://semver.org/) for versioning.

## Authors

* **Sean McQuay** - *Initial work* - [GitHub](https://github.com/srm985) - [Website](http://www.seanmcquay.com)

See also the list of [contributors](https://github.com/srm985/mok-project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/srm985/mok-project/blob/master/LICENSE) file for details.

## Change Log

#### Version 1.1

In this release I have addressed several issues related to how the keyboard handles various input types. Beyond that, I have implemented regular expressions to handle input attribute validations. The keyboard also now respects the attributes 'disabled' and 'readonly'. Added the object inputAttributes to collect and organize these attributes.

#### Version 1.1.1

* Revised build scripts from Grunt to Gulp.
* Cleaned up code base.

#### Version 1.1.2

* Added option to support showing the currently-displayed language.

#### Version 1.1.3

* Added ability to define language key text color.

#### Version 1.1.4

* Added CDN serving capability!
* Allow mapping from language system file name to native language name.
* Added the ability to configure the keyboard to only activate on specified input fields.

#### Version 1.1.5

* Revised code to search local languages first, then pull from CDN.

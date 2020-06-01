# MediaMonks - Frontend Coding Standards

[Based on Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript/)

## Naming
Choosing good names is critical to creating code that is easy to use and easy to understand. You should always take the time to think about whether you have chosen the right name for something, especially if it is part of the public API.

#### English
All code, names, comments, etc. must be in English.
> Tip: install a spell checker in your IDE to avoid typos.

#### Use one name for one thing
Do not reuse names. Do not use names that can mean multiple things. Always use the same name for the same thing. So use the same name within the JavaScript, CSS and HTML for the same thing. Align naming with the whole team: Backend, Frontend, UX, Design, PM, client, etc.

For big projects with their own jargon it could help to create a dictionary.

#### Descriptive
Names must be descriptive for the working or usage of the class, method or variable.

###### The name should always end with what the object is.
For example: a button must always end with `Button`.
 * `MenuButton` a button used in the menu
 * `ButtonMenu` a menu with buttons
 * `MenuButtonIcon` an icon in the button of the menu
 
There is no limit for the length of a name, so prefer a long name which is clear and descriptive than a short name which is not clear.

#### Abbreviations
Avoid them as a general rule. For example, `calculateOptimalValue()` is a better method name than `calcOptVal()`. Being clear is more important than minimizing keystrokes. If you don't abbreviate, developers won't have to remember whether you shortened a word like _qualified_ to `qual` or `qlfd`.

Abbreviations that are part of the HTML, CSS and/or JavaScript API are allowed, like:
 * `URL` for Uniform Resource Locator
 * `URI` for Uniform Resource Identifier
 * `src` for source
 * `DOM` for Document Object Model
 * `img` for image
 
You should only use these abbreviations within the same context. So only use `img` if you refer to an HTML Image Tag. (`<img>`)

We have standardized on a few abbreviations that are allowed to use:
 * `auto` for automatic, as in `autoLayout`
 * `bin` for binary
 * `info` for information, as in `GridRowInfo`
 * `min` for minimum, as in `minWidth`
 * `max` for maximum, as in `maxHeight`
 * `regExp` for regular expression, as in `RegExpValidator`
 * `util` or `utils` for utility or utilities, as in `StringUtils`
 * `id` for identifier. Please note that 'd' should be written in lowercase when used in combination with an other word, like `userId`.
 * `init` for initialize
 * `ui` for user interface
 * `temp` for temporary
 * `app` for application
 * `lib` for library
 * `fps` for frames per second
 * `args` for arguments
 * `param` for parameter
 * `params` for parameters
 * `ref` for reference

#### Plural or singular?

##### Classes
When you would instantiate or type the class it must have singular name, also for enums.
When you should not instantiate the class, it should have a plural name.

##### Arrays
or other kind of lists should have a plural name or end with `List`, like `userList`.

##### Folders
If a folder holds multiple files, but all related to one main type, it should have a singular name. If it holds multiple main files of a type, it should have a plural name.

For example, the folder `page` contains a single page, with maybe some helper files. The folder `pages` contains multiple pages.   

#### Functions
Prefer using a verb as a name to indicate it will do something. Like `render` or `open`.

#### Classes, variables, properties, etc.
All non-functions should have a noun as a name, not a verb.

#### Booleans
Should start with `is`, `has`, `will` or `should`. Like `isValid` or `hasValues`.

#### Always Affirmative
Avoid negations. _“Don’t ever not avoid negative logic”_. Prefer `isShown` over `isHidden` or `isEnabled` over `isDisabled`. Do not use names like `notEditable`.

#### Casing

##### Classes, Interfaces & Types
Are written in Pascal Case naming (start with a capital, the rest camelcase), no underscores, no dashes.


##### Functions, properties, arguments and variables
Are all written in lower camelCase. 


## Coding
Every function or class should do **one thing** (and do it good). If it needs to do more than one thing, split it up. Keep your files, classes and functions small. It’s okay to have a file with just a single line.

#### Pure functions
Prefer writing pure functions, which means they do not manipulate the input arguments or reference/manipulate global state. This makes your code better scalable and testable.


#### Separate Logic From Configuration
Write code that is reusable, scalable and testable.


#### Do not repeat yourself (DRY)

* Do not copy code to another place.
* Avoid using the same string twice in a project.
* Move shared logic to a shared place.
* Make sure you do not have to adapt changes on multiple places.

#### Do not use Magic Numbers
See https://en.wikipedia.org/wiki/Magic_number_(programming)

## Formatting
All code within a project should have the same formatting. To enforce that we use [Prettier](https://prettier.io/).

## Comments
#### Documentation comments
Reconsider if your code really needs comments. Code should be self explaining. Code that needs comments is probably bad.

#### Regular Expressions
Since regular expressions can be hard to read, they should have a comment that indicate what they do. Especially when they are complex.

#### Commented out code
Don't leave commented out code into project. You can always find it back in the version control system. If for some reason you want to keep commented out code in the project, add a comment explaining why it is commented out.

#### TODO
If something needs to be changed or refactored later, add a `// TODO ` comment to indicate what the issue is.

## TypeScript
Use TypeScript in strict mode and do not allow native JavaScript. Therefore everything must be typed. It’s not needed to type something when TypeScript can resolve the type.

#### Access Modifiers
Keep your code as strict as possible, so keep all functions and properties `private` unless they have to be `protected` or `public`.

#### Readonly
In order to be as strict as possible, every property should be set to readonly unless it should writable.

#### Arrays
Always prefer `ReadonlyArray` over a regular `Array` unless it must be possible to modify the Array.

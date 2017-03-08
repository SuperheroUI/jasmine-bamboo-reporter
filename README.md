# jasmine-bamboo-reporter

> A reporter for Jasmine which produces a report compatible with Atlassian Bamboo Mocha Test Parser. This support is handled by locking the results file and then merging with any previous results.

## Installation

```sh
npm install jasmine-bamboo-reporter
```

## Usage

### Jasmine Usage
```javascript
var JSONReporter = require('jasmine-bamboo-reporter');
jasmine.addReporter(new JSONReporter({
	file: 'jasmine-results.json', // by default it writes to jasmine.json
	beautify: true,
	indentationLevel: 4 // used if beautify === true
}));

//ensure there are no lock files and no previous results to merge against.
if (fs.existsSync("jasmine-results.json.lock")) fs.unlinkSync("jasmine-results.json.lock");
if (fs.existsSync("jasmine-results.json")) fs.unlinkSync("jasmine-results.json");

[MIT](https://github.com/voidberg/jasmine-bamboo-reporter/blob/master/LICENSE)

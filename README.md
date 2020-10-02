# NodeJS Console Logger
A powerful and efficient JavaScript logger for NodeJS

```
npm install node-console-logger
```

## Getting Started

### Logger (No File Support)
```js
const NodeLogger = require("node-console-logger");
const Logger = new NodeLogger();
```

### Logger (File Support)
```js
const NodeLogger = require("node-console-logger");
const Logger = new NodeLogger({ dirPath: __dirname + "/log" });
```

### Logger Basics
```js
const NodeLogger = require("node-console-logger");
const Logger = new NodeLogger({ dirPath: __dirname + "/log" });

Logger.on("log", log => { /* Code */ }) // Emits when logging with any method
Logger.on("error", err => { /* Code */ }); // Emits when doing `Logger.error();`

Logger.log("Plain log");
Logger.log("&6Logger&r with &3colour");
Logger.eventLog("Log with no event emit"); // Look at "test/break.js" as why this exists

Logger.history.last(2); // Get the last 2 logs
Logger.fileHistory.getCurrentLog().then(lines => Logger.eventLog(lines)); // Log an array of lines from the latest log file
```

## Test Scripts
In the project directory you an run the following scripts:

### `npm run log`
Will run a sample of the Logger's log methods and events
Located at *test/log.js*

### `npm run history`
Will run a sample of Logger's history and file history
Located at *test/history.js*

### `npm run break`
Will run a file which is designed to break Logger
Used for educational purposes. eventLog() is to prevent this.
Located at *test/break.js*

## Colour Codes
**PREFIX**: `&`

### SPECIAL
**RESET**: `r`
**REVERSE**: `k`

### Format
**BOLD**: `l`
**ITALIC**: `o`
**UNDER**: `n`
**STRIKE**: `m`

### Colour
**FOREGROUND**: `-`
**BACKGROUND**: `_`
**EXAMPLE**: `&-5`

**DARK RED**: `4`
**BRIGHT RED**: `c`

**DARK YELLOW**: `6`
**BRIGHT YELLOW**: `e`

**DARK GREEN**: `2`
**BRIGHT GREEN**: `a`

**DARK CYAN**: `3`
**BRIGHT CYAN**: `b`

**DARK BLUE**: `1`
**BRIGHT BLUE**: `9`

**DARK PURPLE**: `5`
**BRIGHT PURPLE**: `d`

**DARK WHITE**: `7`
**BRIGHT WHITE**: `f`

**DARK BLACK**: `0`
**BRIGHT BLACK**: `8`
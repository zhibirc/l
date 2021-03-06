[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](license.md)
[![Maintenance](https://img.shields.io/maintenance/yes/2019.svg?style=flat-square)]()

## Usage

```bash
npm i gdebug -D
```

[probing...](api.md)


### Functionality

**WIP**


### Built-in Log Levels

The built-in log levels have a set of convenience methods on the Logger interface that makes them easier to use.

Level | Description
------|------------------------------------
ALL   | All levels including custom levels.
TRACE | Designates finer-grained informational events than the DEBUG.<br>Most detailed information. Expect these to be written to logs only.  
DEBUG | Designates fine-grained informational events that are most useful to debug an application.<br>Expect these to be written to logs only. Generally speaking, most lines logged by your application should be written as DEBUG.
INFO  | Designates informational messages that highlight the progress of the application at coarse-grained level.<br>Interesting runtime events (startup/shutdown). Expect these to be immediately visible on a console, so be conservative and keep to a minimum.
WARN  | Designates potentially harmful situations. Expect these to be immediately visible on a status console.<br>Use of deprecated APIs, poor use of API, "almost" errors, other runtime situations that are undesirable or unexpected, but not necessarily "wrong".
ERROR | Designates error events and unexpected conditions that might still allow the application to continue running.<br>Expect these to be immediately visible on a status console.
FATAL | Designates very severe error events that will presumably lead the application to abort.<br>Expect these to be immediately visible on a status console.
OFF   | The highest possible rank and is intended to turn off logging.


### How do Levels Works?

A log request of level **X** in a logger with level **Y** is enabled if `X >= Y`. It assumes that levels are ordered. 
For the standard levels, we have `ALL < TRACE < DEBUG < INFO < WARN < ERROR < FATAL < OFF`.

 
### Adding Custom Log Levels

**gdebug** supports custom log levels. Custom log levels can be defined in code. To define a custom log level in code, use the `<Logger_instance>.defineLevel(config)` method. 
This method creates a new level for the specified logger with particular properties (e.g. `name`). After a log level is defined you can log messages at this level. 


### Replacing Log Levels

If it were possible to hide existing log levels, users could customize the Logger interface to match their requirements. 
Some people may not want to have a FATAL or a TRACE level, for example. They would like to be able to create a custom Logger that only has debug(), info(), warn() and error() methods.


### Adding a Handler

The default logger will use a Console Handler if you don't specify anything else. You can add handlers to any logger:

[probing...](api.md)

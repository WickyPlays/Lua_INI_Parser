## About this repository

This is a simple INI file parser with Lua, allowing modification of .ini from Lua codes. Supports comments, keeping line orders, avoiding empty line cutting, and more.

## How to use?

+ Copy `ini_parser.lua` script from this repository and paste it anywhere in your project directory.<br />
+ Get functions from `ini_parser.lua` via require (EX: `local ini_parser = require('ini_parser")`<br />
+ That's it!

## API usage

* __ini_parser.read(fileName)__ : Returns a table containing all the values from the file.
* __ini_parser.write(fileName, data)__ : Saves the data into the specified file.

## Example usage

### Writing to `config.ini`:

```lua

local ini_parser = require('ini_parser')

-- Create data to write to the INI file
local data = {
    Settings = {
        resolution = "1920x1080",
        fullscreen = true
    },
    User = {
        username = "player1",
        highscore = 5000
    }
}

-- Write the data to the INI file
ini_parser.write('config.ini', data)

```

Result would look like this:
```ini
[Settings]
resolution=1920x1080
fullscreen=true

[User]
username=player1
highscore=5000
```
### Reading from `config.ini`:
```lua
local ini_parser = require('ini_parser')

local data = ini_parser.read('config.ini')
--[[ This returns:
local data = {
    Settings = {
        resolution = "1920x1080",
        fullscreen = true
    },
    User = {
        username = "player1",
        highscore = 5000
    }
}
]]

```
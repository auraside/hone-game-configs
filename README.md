# Game Configs

# Creating an `info.json` File for Game Settings Compiler/Parser

You're creating an `info.json` file that will guide a game settings compiler and parser to manage game configuration files. This `info.json` file contains information about the game, configuration settings, and how to map keys to specific configuration fields.

## Initial Fields

```js
{
  "name": "folder_and_gameName_here", //Minecraft
  "ignore_fields": ["field_name_here"], //["volume", "adsp_debug"]
  "mappings": {}
}
```

- name: The name of the game and the name of the folder where the info.json file is located. In this case, the info.json file would be located at CSGO/info.json.

- ignore_fields: Fields that will be ignored by the parser/compiler and will not be stored by Hone backend.

- mappings: An object where you define how the game's setting keys map to configuration fields.

## `ignore_fields` Array

The `ignore_fields` array configuration prevents sensitive data, like passwords and user-related information, from being stored or exposed by the backend.

Example:

```json
{
  "ignore_fields": ["password", "auth_token"]
}
```

## Mapping Fields

You use the "mappings" object to define how fields from the game's configuration relate to the fields in the backend. Each entry in the "mappings" object explains how to map a specific game config setting to a database field.

`mappings` is an object itself that contains individual mappings like the following example:

```json
"Texture": {
  "key": "texture_quality",
  "type": "string",
}
```

- the key of the object which is Texture in the above example is the key of the field of the config file.
- key: This indicates the corresponding configuration field key to read from or write to. It should match one of the field names in the game settings database.
- type: This is where you specify a type system for mapping within the info.json.

## Type System in Mapping

The type field determines how the game setting should be interpreted and mapped to the configuration field. Here are the types and their meanings:

### 1. Boolean ["boolean"]

```json
"InvertAxisY": {
  "key": "mouse_invertYAxis",
  "type": "boolean",
  "isNumber": false
}
```

- type: Specifies that the game setting is a boolean (true/false) value.
- isNumber: If true, indicates that the config field boolean value is represented as 0/1 instead of true/false.

### 2. String ["string"]

```json
"AspectRatio": {
  "key": "resolution_aspectRatio",
  "type": "string"
}
```

- type: Indicates that the game setting is a text-based value.

### 3. Progress ["progress"]

```json
"Volume": {
  "key": "master_volume",
  "type": "progress",
  "min": 0,
  "max": 1
}
```

- type: Used for settings that represent a progress value, like a volume slider.
- min: The minimum value of the progress in the config file.
- max: The maximum value of the progress in the config file.

### 4. Select Object ["select_object"]

```json
"AntiAliasingMethod": {
  "key": "anti_aliasing",
  "type": "select_object",
  "options": {
    "0": "Off",
    "1": "FXAA",
    "2": "MSAA",
    "3": "SSAA",
    "4": "MLAA"
  }
}
```

- type: Used for settings that have predefined options.
- options: An object mapping possible values in the configuration field to corresponding possible values of the field of game setting database

### 5. Select Array ["select_array"]

```json
"control_type": {
  "key": "control_type",
  "type": "select_array",
  "options": ["mouseandkeyboard", "joystick"]
}
```

- type: Similar to "Select Object," but options are provided in a simple array.
- options: Simple array of possible options

### 6. Value Replacement using Regex

Uses a regex (regular expression) to replace a value in a configuration field. Its for those cases where other type cases do not work.

```js
'bind "$hone_value" "run"': {
  "key": "bind_run",
  "isRegex": true
}
```

- The $hone_value indicator specifies where the value actually exists.
- The isRegex flag must be true for this to work.

# Example `info.json` file

```json
{
  "name": "CSGO",
  "ignore_fields": [
    "volume",
    "adsp_debug",
    "ai_report_task_timings_on_limit",
    "ai_think_limit_label"
  ],
  "mappings": {
    "volume": {
      "key": "master_volume",
      "type": "progress",
      "min": 0,
      "max": 1
    },
    "snd_musicvolume": {
      "key": "background_music",
      "type": "progress",
      "min": 0,
      "max": 1
    },
    "voice_scale": {
      "key": "speech_volume",
      "type": "progress",
      "min": 0,
      "max": 1
    },

    "cc_subtitles": {
      "key": "subtitles",
      "type": "boolean",
      "isNumber": true
    },
    "sys_antialiasing": {
      "key": "anti_aliasing",
      "type": "select_object",
      "options": {
        "0": "Off",
        "1": "FXAA",
        "2": "MSAA",
        "3": "SSAA",
        "9999999": "MLAA"
      }
    },
    "sensitivity": {
      "key": "mouse_sensitivity",
      "type": "progress",
      "min": 0,
      "max": 100
    },
    "sk_autoaim_mode": {
      "key": "mouse_autoAim",
      "type": "boolean",
      "isNumber": true
    },

    "bind \"$hone_value\" \"+speed; r_cleardecals\"": {
      "key": "controls_walk",
      "isRegex": true
    },

    "bind \"$hone_value\" \"+forward\"": {
      "key": "controls_up",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+back\"": {
      "key": "controls_down",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+moveleft\"": {
      "key": "controls_left",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+moveright\"": {
      "key": "controls_right",
      "isRegex": true
    },

    "bind \"$hone_value\" \"+jump\"": {
      "key": "controls_jump",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+use\"": {
      "key": "controls_use",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+attack\"": {
      "key": "controls_fire",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+attack2\"": {
      "key": "controls_fireSecondary",
      "isRegex": true
    },
    "bind \"$hone_value\" \"buymenu\"": {
      "key": "controls_menu",
      "isRegex": true
    },
    "bind \"$hone_value\" \"+duck\"": {
      "key": "controls_crouch",
      "isRegex": true
    },
    "control_type": {
      "key": "joystick",
      "type": "select_object",
      "options": {
        "0": "mouseandkeyboard",
        "1": "joystick"
      }
    }
  }
}
```

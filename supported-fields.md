# Officially supported fields

Below is the detailed list of all the game-related supported fields by Hone

##Game Settings

### Fields

1. **name**

   - **Type:** `String`
   - **Description:** Represents the name of the game settings.

2. **description**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Provides a description of the game settings. Can be null or empty if not specified.

3. **graphics**

   - **Type:** `One-to-One Relationship with Graphics`
   - **Description:** Defines the graphical settings associated with this game setting.

4. **controls**

   - **Type:** `One-to-One Relationship with Controls`
   - **Description:** Specifies the control settings associated with this game setting.

5. **audio**

   - **Type:** `One-to-One Relationship with Audio`
   - **Description:** Specifies the audio settings associated with this game setting.

6. **extra_settings**
   - **Type:** `JSON (Nullable - Can be empty)`
   - **Description:** Additional settings that are not supported by Hone officially stored in JSON format that extend the game settings. Can be null or empty if not provided.

##Graphics

### Fields

1. **resolution_height**

   - **Type:** `Number (Nullable - Can be empty)`
   - **Description:** Represents the height of the resolution for graphics. Can be null or empty if not specified.

2. **resolution_width**

   - **Type:** `Number (Nullable - Can be empty)`
   - **Description:** Represents the width of the resolution for graphics. Can be null or empty if not specified.

3. **resolution_aspectRatio**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Represents the aspect ratio of the resolution for graphics. Can be null or empty if not specified.

4. **texture**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Specifies the texture settings for graphics. Can be null or empty if not specified.

5. **anti_aliasing**
   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Defines the anti-aliasing settings for graphics. Possible values: 'Off', 'FXAA', 'MSAA', 'SSAA', 'MLAA'. Can be null or empty if not specified.

##Audio

### Fields

1. **master_volume**

   - **Type:** `Number (Nullable - Can be empty)`
   - **Description:** Represents the master volume setting for audio. Can be null or empty if not specified.

2. **background_music**

   - **Type:** `Number (Nullable - Can be empty)`
   - **Description:** Represents the volume level for background music. Can be null or empty if not specified.

3. **speech_volume**

   - **Type:** `Number (Nullable - Can be empty)`
   - **Description:** Represents the volume level for speech/audio dialogues. Can be null or empty if not specified.

4. **subtitles**
   - **Type:** `Boolean (Nullable - Can be empty)`
   - **Description:** Indicates whether subtitles are enabled for the game's audio. Can be null or empty if not specified.

##Controls

### Fields

1. **control_type**

   - **Type:** `'mouseandkeyboard' | 'joystick' (Nullable - Can be empty)`
   - **Description:** Specifies the type of control used, either 'mouseandkeyboard' or 'joystick'. Can be null or empty if not specified.

2. **mouse_sensitivity**

   - **Type:** `Number (Decimal with precision 10 and scale 2) (Nullable - Can be empty)`
   - **Description:** Represents the sensitivity of the mouse control. Can be null or empty if not specified.

3. **mouse_invertXAxis**

   - **Type:** `Boolean (Nullable - Can be empty)`
   - **Description:** Indicates whether the X-axis for mouse control is inverted. Can be null or empty if not specified.

4. **mouse_invertYAxis**

   - **Type:** `Boolean (Nullable - Can be empty)`
   - **Description:** Indicates whether the Y-axis for mouse control is inverted. Can be null or empty if not specified.

5. **mouse_autoAim**

   - **Type:** `Boolean (Nullable - Can be empty)`
   - **Description:** Indicates whether auto-aim is enabled for mouse control. Can be null or empty if not specified.

6. **controls_up**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Represents the key/button for the 'up' control. Can be null or empty if not specified.

7. **controls_down**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Represents the key/button for the 'down' control. Can be null or empty if not specified.

8. **controls_left**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Represents the key/button for the 'left' control. Can be null or empty if not specified.

9. **controls_right**

   - **Type:** `String (Nullable - Can be empty)`
   - **Description:** Represents the key/button for the 'right' control. Can be null or empty if not specified.

10. **controls_strafe**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'strafe' control. Can be null or empty if not specified.

11. **controls_run**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'run' control. Can be null or empty if not specified.

12. **controls_toggleRun**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for toggling the 'run' control. Can be null or empty if not specified.

13. **controls_walk**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'walk' control. Can be null or empty if not specified.

14. **controls_toggleWalk**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for toggling the 'walk' control. Can be null or empty if not specified.

15. **controls_jump**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'jump' control. Can be null or empty if not specified.

16. **controls_use**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'use' control. Can be null or empty if not specified.

17. **controls_fire**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'fire' control. Can be null or empty if not specified.

18. **controls_fireSecondary**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the secondary 'fire' control. Can be null or empty if not specified.

19. **controls_menu**

    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'menu' control. Can be null or empty if not specified.

20. **controls_crouch**
    - **Type:** `String (Nullable - Can be empty)`
    - **Description:** Represents the key/button for the 'crouch' control. Can be null or empty if not specified.

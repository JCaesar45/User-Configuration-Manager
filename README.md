```
# User Configuration Manager

A Python implementation for managing user configuration settings such as theme, language, and notifications. This module provides functions to add, update, delete, and view user settings with proper validation and formatting.

## Features

- **Add Settings**: Add new configuration settings with key-value pairs
- **Update Settings**: Modify existing configuration settings
- **Delete Settings**: Remove configuration settings
- **View Settings**: Display all current settings in a formatted way

## Functions

### `add_setting(settings, key_value)`
Adds a new setting to the configuration dictionary.

**Parameters:**
- `settings` (dict): The dictionary containing user settings
- `key_value` (tuple): A tuple containing (key, value) pair to add

**Returns:**
- Success message if setting was added
- Error message if setting already exists

**Behavior:**
- Converts both key and value to lowercase
- Prevents duplicate keys

**Example:**
```python
settings = {'theme': 'light'}
result = add_setting(settings, ('Volume', 'High'))
# Returns: "Setting 'volume' added with value 'high' successfully!"
# Settings becomes: {'theme': 'light', 'volume': 'high'}

update_setting(settings, key_value)
Updates an existing setting in the configuration dictionary.

Parameters:

settings (dict): The dictionary containing user settings
key_value (tuple): A tuple containing (key, value) pair to update
Returns:

Success message if setting was updated
Error message if setting doesn't exist
Behavior:

Converts both key and value to lowercase
Only updates existing keys
Example:

settings = {'theme': 'light'}
result = update_setting(settings, ('Theme', 'Dark'))
# Returns: "Setting 'theme' updated to 'dark' successfully!"
# Settings becomes: {'theme': 'dark'}

delete_setting(settings, key)
Deletes a setting from the configuration dictionary.

Parameters:

settings (dict): The dictionary containing user settings
key (str): The key of the setting to delete
Returns:

Success message if setting was deleted
Error message if setting doesn't exist
Behavior:

Converts key to lowercase
Only deletes existing keys
Example:

settings = {'theme': 'light', 'volume': 'high'}
result = delete_setting(settings, 'VOLUME')
# Returns: "Setting 'volume' deleted successfully!"
# Settings becomes: {'theme': 'light'}

view_settings(settings)
Displays all current settings in a formatted way.

Parameters:

settings (dict): The dictionary containing user settings
Returns:

Formatted string showing all settings
"No settings available." if dictionary is empty
Behavior:

Capitalizes the first letter of each setting name
Formats each setting on a new line
Example:

settings = {'theme': 'dark', 'notifications': 'enabled', 'volume': 'high'}
result = view_settings(settings)
# Returns:
# "Current User Settings:
# Theme: dark
# Notifications: enabled
# Volume: high
# "

Testing
The module includes a test_settings dictionary for testing purposes:

test_settings = {
    'theme': 'light',
    'notifications': 'enabled',
    'volume': 'medium'
}

You can use this dictionary to test all functions:

# Add a new setting
add_setting(test_settings, ('language', 'english'))

# Update an existing setting
update_setting(test_settings, ('theme', 'dark'))

# Delete a setting
delete_setting(test_settings, 'notifications')

# View all settings
print(view_settings(test_settings))

Implementation Notes
All keys are stored and processed in lowercase for consistency
Values are also converted to lowercase when added or updated
The functions validate operations before modifying the settings
The view_settings function formats output with capitalized keys and proper line breaks

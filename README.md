# MMM-ViewNotifications

This is a module for the [MagicMirror²](https://github.com/MichMich/MagicMirror/).

This module is intended to assist with module development.  It displays a list of notifications that have been broadcast to all the modules.  

| Status | Version | Date | Maintained? |
|------- |-------- |----- |------------ |
| Working | `1.0.0` | 2018-05-07 | Yes |

## Example
![Screenshot of MMM-ViewNotifications](/images/sample.png?raw=true "Example screenshot")

## Installation
To install the module, use your terminal to:
1. Navigate to your MagicMirror's modules folder.  If you are using the default installation directory, use the command:<br />`cd ~/MagicMirror/modules`
2. Copy the module to your computer by executing the following command:<br />`git clone https://github.com/glitch452/MMM-ViewNotifications.git`

## Using the module

To use this module, add the following configuration block to the modules array in the `config/config.js` file:
```js
var config = {
    modules: [
        {
            module: 'MMM-ViewNotifications',
            position: "top_left",
            header: "Notifications",
            config: {
                // See below for configurable options
            }
        }
    ]
}
```

## Configuration options

| Option                 | Description
|----------------------- |--------------
| `timeout`              | *Optional* - How long (in seconds) the notification should stay on the screen, set to 0 to keep indefinitely<br />**Type:** `number`<br />**Default:** `8`
| `maximum`              | *Optional* - The maximum number of notificaitons to show, set to 0 for unlimited (New ones push out older ones)<br />**Type:** `number`<br />**Default:** `8`
| `icons`                | *Optional* - The icons to use for notifications from specific modules<br />**Type:** `object`<br />**Default:** `{ calendar: 'calendar', clock: 'clock-o', currentweather: 'thermometer', weatherforecast: 'thermometer' }`
| `defaultIcon`          | *Optional* - The default icon to use for a module whos icon is not set in the icons list<br />**type:** `string`<br />**Default:** `'bullhorn'`
| `newestOnTop`          | *Optional* - If true, new notifications are added to the top of the list, if false, the bottom<br />**Type:** `boolean`<br />**Default:** `true`
| `includeModules`       | *Optional* - A white list of modules, if not empty, only notifications from these modules will be displayed<br />**Type:** `array`<br />**Default:** `[]`
| `excludeModules`       | *Optional* - A black list of modules, notifications from these modules will not be displayed<br />**Type:** `array`<br />**Default:** `[]`
| `includeNotifications` | *Optional* - A white list of notifications, if not empty, only notifications of these types will be displayed<br />**Type:** `array`<br />**Default:** `[]`
| `excludeNotifications` | *Optional* - A black list of modules, notifications of these types will not be displayed<br />**Type:** `array`<br />**Default:** `[]`
| `format`               | *Optional* - The format to use for the notification item added to the list. <br />**Type:** `string`<br />**Default:** `'{time}: "{module}" sent "{notification}"'`<br />**Options:** <br /> - `{notification}`  The name of the notification<br /> - `{module}`  The name of the module that sent the notification<br /> - `{payloadList}`  A list of properties in the payload object<br /> - `{payloadData}`  A JSON string representing the payload data in the notification<br /> - `{date}`  The date that the notification was sent in the YYYY-MM-DD format<br /> - `{time}`  The date that the notification was sent in the HH:mm:ss format<br /> - `{date\|format}`  The date/time that the notification was sent, in the specified format, <br />using [moment.js](https://momentjs.com/docs/#/displaying/format/) for formatting rules.  Ex: {date\|HH:mm}

## Updates
To update the module to the latest version, use your terminal to:
1. Navigate to your MMM-ViewNotifications folder.  If you are using the default installation directory, use the command:<br />`cd ~/MagicMirror/modules/MMM-ViewNotifications`
2. Update the module by executing the following command:<br />`git pull`

If you have changed the module on your own, the update will fail.  <br />To force an update (WARNING! your changes will be lost), reset the module using and retry the update with the following commands:
```
git reset --hard
git pull
```

## License

### The MIT License (MIT)

Copyright © 2016 David Dearden

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

**The software is provided “as is”, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.**
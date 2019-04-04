# Slack Night Mode
A user style for easy Slack theming. [CC0](http://creativecommons.org/publicdomain/zero/1.0/).
Originally from [laCour](https://github.com/laCour/slack-night-mode), modified for better styling.

## How To enable Dark Mode in the Slack app
(Instructions are specifically for macOS. It should be similar in Windows by going to `Program Files` instead).
1. Go to `~/Applications` and right click `Slack.app`, and click `Show Package Contents`.
2. Open `Contents/Resources/app.asar.unpacked/src/static/ssb-interop.js`
3. Insert the below code at the very end of the file

```js
document.addEventListener('DOMContentLoaded', function() {
  $.ajax({
    url: 'https://raw.githubusercontent.com/jayhxmo/slack-night-mode/master/css/black.css',
    success: function(css) {
      $('<style></style>')
        .appendTo('head')
        .html(css);
    }
  });
});
```
4. Save and exit, and launch Slack!

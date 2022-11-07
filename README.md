# Chat-Archive in "MS Teams-Style"
The idea was to style a static chat-archive like in MS Teams. Without a webserver, just as a static (and standalone) html file.

It is based on the styling used in the [Azure Communication UI Lib](https://github.com/Azure/communication-ui-library) that is based on [Fluent UI](https://github.com/microsoft/fluentui).

## Easy Solution v1
I reformatted the html into a proper html file, removed the `<thead>`, the outline of the inner HTML of the chat-content and some more unnecessary table columns and rows and did a simple styling with the given HTML-Tags and a bit nth-child-Magic.   
[Check the browser compatibility of nth-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child?retiredLocale=de#browser_compatibility)

-> The CSS is in every example written in an extra file, but could also be directly included with `<style>` into the HTML files.

The styles are basically 98% copied.

## Easy Solution v2
I did the same as in v1, but used proper CSS-Classes instead of nth-child-Magic. In my opinion it should be possible to generate a proper html file with the given CSS-Classes without too much more effort.

## Medium Solution
With some more data-preprocessing this solution is closer to what a MS Teams-Chat looks like. I removed the complete table structure and used `<div>`s instead. I also added some more styling to highlight the messages I as the user wrote and wrapped the sender and the date into another `<div>` to make let it look even more like Teams.
It's not much but it imrpoves the UI a bit from [v1](#Easy-Solution-v1) and [v2](#Easy-Solution-v2).

## Advanced Solution(s)
What could be more advanced solutions with a higher User-Experience and a better chance to get accepted and used:
* step away from the idea of only using a static HTML file and use a node.js based project and use the [Azure Communication UI Lib](https://github.com/Azure/communication-ui-library) properly and add an API-Call or and Azure Function or something similar to read the data dynamically
* add an onload-Event Javascript Part to iterate through JSON-Files, generate a proper menu and load the corresponding chat into the HTML-File (more CSS would be needed as well)
* ...

## More thoughts
* this little project and the user acceptance rises and falls with the pre-processing of the data
* the expectation that it is only "adding a little css here and there and that should be easily done" is right as long as you do not expect a good solution with a good user experience
* for such a use case I expect just a few people to use it, so I would not invest too much time in it and [easy v1](#Easy-Solution-v1), [easy v2](#Easy-Solution-v2) or [medium](#Medium-Solution) should be enough - effort and benefit must remain in proportion







Example image by [Kellie Churchman via pexels](https://www.pexels.com/@kellie-churchman-371878/)
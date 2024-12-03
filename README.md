# Uncommon HTML DOM Manipulation Bug

This repository demonstrates a subtle bug related to DOM manipulation in HTML. The bug arises from attempting to modify the innerHTML of a div element before it's fully loaded into the DOM.  The solution involves using the DOMContentLoaded event or placing the script at the end of the body.

## Bug Description
The script attempts to modify the content of a div element (`myDiv`)  before the element is fully parsed by the browser. This results in either no change or a JavaScript error in strict mode.  Adding a new element AFTER modifying the existing one will also cause problems if the first operation fails.

## Bug Solution
The solution ensures the script executes after the DOM is fully parsed and ready. This is typically done by either:

1. Placing the script at the very end of the `<body>` element, after all other elements.
2. Attaching the script execution to the `DOMContentLoaded` event.

The solution provided uses the second approach.
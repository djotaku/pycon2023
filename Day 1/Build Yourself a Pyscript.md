# Build Yourself a Pyscript

in the body of html there's a tag <py-script>

Also you need a script tag with src=pyscript.js

micropython was originally intended for microcontrollers. Turns out it's also great for pyscript since it has a very small size compared to the cPython.

Mostly like cPython, but no virtual environments or pip

A lot of focus on making sure things can go more quickly when used in the browser

What about storage? Pyodide has some ability to use storage. 

Pyscript uses web workers so that it doesn't have to block the main UI for browser running, unlike Javascript


Known Issues
============

1. Errors occur when opening a file dialog using tkinter on MacOS 12.0.1.
Please update MacOS or use ``dialog=False`` when loading a file.
This is fixed in MacOS 12.1.0

2. Closing the browser tab doesn't end the interactive session in python.
So far, the only way to do so is to interrupt the kernel running in the background.
Use ctrl+c (in jupyter press the i key twice) to interrupt the kernel
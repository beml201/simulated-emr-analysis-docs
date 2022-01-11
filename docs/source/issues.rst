Known Issues
============

1. Errors occur when opening a file dialog using tkinter on MacOS 12.0.1
Please update MacOS or use ``dialog=False`` when loading a file
This is fixed in MacOS 12.1.0

2. When the interactives open in a browser I can't stop it running in the background.
You should be able to stop it running in the background by interrupting the python kernel
Use ctrl+c (in jupyter press the i key twice) to interrupt the kernel
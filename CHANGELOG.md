# Changelog

## 1.0.0 (2023-11-17)

### Features From Magma

- Start a kernel from a list of kernels
- Attach to already running jupyter kernel
- Send code to the Jupyter Kernel to run asynchronously
- View output in a floating window below the `cell` that you ran, including image outputs
- Cells are saved, and you can rerun them, they expand when you type, and you can pull up their
output again, and rerun them. Interact with the output in a vim buffer

### New Features (pre 1.0.0)

- Completely custom borders
- Border colors per run status
- "Cropped" window borders
- Window footer to display the number of extra lines that don't fit in the window
- configurable max window size
- Can specify no border without minimal style
- Buffers can be shared across kernels `:MoltenInit shared [kernal]`
- You can have multiple kernels running in one buffer, including the same kernel running more than
once
- Update configuration values on the fly
- Enter output can also open the output so you have one key to do both
- You can hide the output without leaving the cell
- Quitting an output window hides the output window (configurable)
- A function for running a range of lines, enabling user created code runners
- 
- Image rendering
    - Images are rendered with Image.nvim which has support for kitty and uberzug++. Much more
    consistent image rendering.
    - Configurable max image height
    - Allows for cropped images
    - CairoSVG is no longer required for rendering svg. The ImageMagic dependency of Image.nvim
    handles that for us
    - more image formats supported
- More graceful LaTeX image rendering errors
- `:MoltenInfo` command to see information about kernels
- Status line functions to see running kernels and/or initialization status


### Bug Fixes

- Kernel prompt actually works when used from the command line
- Close output command works from inside an output window
- Folding text above an output window is correctly accounted for
    - Similarly, virtual lines are correctly accounted for
- Window rendering performance: No longer redraw an open window ever, it's just updated
- Cell rendering performance: Don't redraw the cell highlights every time the window scrolls or the
cursor moves
- Run status is working again
- Save/load is working again
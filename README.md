# Cell Shader
### By Snowy
*IMPORTANT: all inputs must be in ".jpg" format

---


1. First, we import the necessary libraries: `cv2` for image processing, `numpy` for numerical operations, `PIL` for image manipulation, `ipywidgets` for creating interactive widgets, and `IPython.display` for displaying the output.

2. We define the path to the input image file.

3. The `image` variable is used to load the input image using `Image.open()` from the PIL library.

4. We create a `FloatSlider` widget named `threshold_slider` to adjust the threshold value. The slider ranges from 0.0 to 1.0 with a step size of 0.01. It is initially set to a value of 1.0. This slider will be used to control the threshold for the edge detection process.

5. An output widget named `output_image` is created. This widget will be used to display the cell-shaded image.

6. The `update_cell_shading()` function is defined. This function takes the threshold value as input and updates the cell-shaded image based on that value. Here's what it does:
   - Convert the input image to grayscale using the `convert()` method from PIL.
   - Apply color quantization to reduce the number of colors in the image using the `posterize()` method from PIL. The number of colors is set to 8.
   - Perform edge detection using the Canny algorithm from the `cv2` library. The threshold value is scaled to the range 0-255 and applied to the `Canny()` function.
   - Clear the output widget and display the updated cell-shaded image using the `Image.fromarray()` method from PIL.

7. The `interactive()` function from `ipywidgets` is used to link the `update_cell_shading()` function with the `threshold` parameter of the `threshold_slider` widget. This ensures that the `update_cell_shading()` function is called whenever the slider value changes.

8. We display the `threshold_slider` and `output_image` widgets using the `display()` function from `IPython.display`.

9. Finally, we initialize the cell-shaded image by calling the `update_cell_shading()` function with the initial value of the `threshold_slider`.

With this code, you can interactively adjust the threshold value using the slider, and the cell-shaded image will update in real-time based on the selected threshold. The number of colors in the cell-shaded image is fixed at 8 due to the threshold slider becoming unable to function properly

# Image Quilting for Texture Synthesis and Transfer

This project implements the image quilting algorithm for texture synthesis and texture transfer, based on the Efros & Freeman SIGGRAPH 2001 paper and Criminisi’s exemplar-based inpainting approach. It incorporates techniques such as random patch quilting, overlapping patches with seam finding, texture transfer, iterative texture refinement, face-in-toast blending, and hole filling using a priority function.

Please refer to the printed version of the Colab file (`bkpark2_proj2.pdf`) in the notebooks folder for the output images.

The `utils.py` file was provided by the instructor, while all other components were custom implemented without any provided templates :).

## Features
- **Randomly Sampled Texture:** Generates an output image by randomly sampling patches.
- **Overlapping Patches:** Uses overlapping patches with SSD-based matching and a tolerance parameter.
- **Seam Finding:** Applies seam cutting (using a provided `cut` function) to remove visible edges.
- **Texture Transfer:** Transfers texture from a sample image to a guidance image.
- **Iterative Texture Transfer:** Refines texture transfer over multiple iterations.
- **Face-in-Toast Blending:** Combines texture transfer with Laplacian pyramid blending to integrate a face into a toast texture.
- **Hole Filling (Priority Function):** Fills circular holes by prioritizing pixels based on solidity and edge strength.

## Installation and Running

1. **Clone the Repository:**
   ```
   git clone https://github.com/YourUsername/image-quilting.git
   cd image-quilting
   ```

2. **Install Dependencies:**
   ```
   pip install -r requirements.txt
   ```

3. **Run the Main Source Code:**
   For example, to run random quilting:
   ```
   python src/image_quilting.py
   ```

4. **Interactive Demo:**
   Alternatively, open the Jupyter Notebook in the `notebooks/` folder using Jupyter or Google Colab for an interactive demonstration.

## Project Details

This project is organized into several parts:

1. **Randomly Sampled Texture:**  
   Uses the `quilt_random` function to create a basic texture quilt.

2. **Overlapping Patches:**  
   The `quilt_simple` function handles overlapping patches and selects candidates using SSD cost and a tolerance parameter.

3. **Seam Finding:**  
   The `quilt_cut` function demonstrates seam finding by cutting along the minimum-cost path in the overlapping region.

4. **Texture Transfer:**  
   Implements guided texture transfer using a mix of overlap cost and guide image cost.

5. **Iterative Texture Transfer:**  
   Refines the texture transfer over several iterations.

6. **Face-in-Toast Blending:**  
   Combines texture transfer with Laplacian pyramid blending to integrate a face into a toast texture.

7. **Hole Filling (Priority Function):**  
   Fills circular holes by computing a priority based on confidence (solidity) and edge strength.

All functions are documented in the source code, and debug visualizations are provided in the notebook.

## Acknowledgments / Attribution

### References
- **OpenCV Hole Filling**  
  Adapted from [Deep Learning Study](https://deep-learning-study.tistory.com/226)
- **Object Removal by Exemplar-Based Inpainting**  
  A. Criminisi, P. Perez, K. Toyama, 2003. [IEEE Xplore Link](https://ieeexplore.ieee.org/document/1216928)
- **iOS Implementation of Exemplar-Based Inpainting**  
  [GitHub Repository](https://github.com/agnivsen/Exemplar?tab=readme-ov-file)

### Image Sources
- **Hole in Wood:** [Wikipedia](https://en.wikipedia.org/wiki/Hole#/media/File:Hole_in_wood.jpg)
- **Ice-Covered Fence:** [Pixabay](https://pixabay.com/photos/fence-bars-cold-winter-ice-grid-8500152/)
- **Roof Tiles Pattern:** [Pixabay](https://pixabay.com/photos/roof-roof-tiles-pattern-house-8193787/)
- **Golf Ball Image:** [Pixabay](https://pixabay.com/photos/golf-green-ball-flag-course-sport-7600947/)

### AI-Assisted Development
- **GitHub Copilot & Google Colab AI:**  
  Used for generating code templates, auto-completing boilerplate code, and refining inpainting logic.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

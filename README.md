# Seam Carving

## Setup

require Python 3.6 or later

```bash
pip3 install -r requirements.txt
jupyter notebook
```

## Running

There are several sections. You need to <ins>run each section in order</ins>. Former parts define functions that are required by latter parts. However, you can skip cells with outputs to save time.

Image transformation is interleaved within the notebook. <ins>All image transformation cells come with outputs</ins>, which can help to locate.

Optionally, you can create video for each result using `make_video(largest_im, im_list, file_name)`.

## Structure

- (prepare)
  - `def im_apply_redline(im_, mask)`
  - `def make_video(im_, ims_, output_path)`
- Step 1: Define the energy function
  - `def energy(im_, use_e1=False)`
- Step 2: Find the minimum seams
  - `def v_cost(energy)`
  - `def h_cost(energy)`
  - `def v_mask(cost, path)`
  - `def h_mask(cost, path)`
- Step 3: Generate the result image (**Seam Carving**)
  - Load Images
    - Note: You can add new images here, and REMEMBER to update `im` pointing to the target image so that input is specified correctly.
  - `def seam_cut(in_, output_height, output_width)`
  - Perform seam cutting
- Extension 1: **Seam Insertion**
  - `def idx_extension_orig_ext(ids)`
  - `def idx_extension_carve_orig(ids,size)`
  - Perform seam insertion
- Extension 2: Seam Carving with Forward Energy
  - `def v_cost_forward(im,P=None)`
  - `def h_cost_forward(im,P=None)`
  - Perform seam cutting w/ forward energy
- Extension 3: **Object Removal**
  - Perform object removal
    - horizontally & vertically
    - w/ & w/o forward energy
- Extension 4: **Content Amplification**
  - Amplify content using forward energy


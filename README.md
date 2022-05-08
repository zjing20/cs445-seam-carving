# Seam Carving

## Setup

require Python 3.6 or later

```bash
pip3 install -r requirements.txt
jupyter notebook
```

## Running

There are several sections. You need to run them in order because former parts contain function definitions that are required by latter parts.

Image transformation is interleaved within the notebook. All image transformation cells come with outputs, which can help to locate.

Optimally you can skip cells with outputs to save time.

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
- Step 3: Generate the result image
  - Load Images
    - Note: You can add new images here, and REMEMBER to update `im` pointing to the target image so that input is specified correctly.
  - `def seam_cut(in_, output_height, output_width)`
  - Perform seam cutting
- Extension 1: Seam Insertion
  - `def idx_extension_orig_ext(ids)`
  - `def idx_extension_carve_orig(ids,size)`
  - Perform seam insertion
- Extension 2: Seam Carving with Forward Energy
  - `def v_cost_forward(im,P=None)`
  - `def h_cost_forward(im,P=None)`
  - Perform seam cutting w/ forward energy
- Extension 3: Object Removal
  - Perform object removal
    - horizontally & vertically
    - w/ & w/o forward energy
- Extension 4: Content Amplification
  - Amplify content using forward energy

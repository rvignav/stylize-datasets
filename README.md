# stylize-datasets

- To stylize a dataset, run `python stylize.py`.
  Arguments:
  - `--content-dir <CONTENT>` the top-level directory of the content image dataset (mandatory)
  - `--style-dir <STLYE>` the top-level directory of the style images (mandatory)
  - `--output-dir <OUTPUT>` the directory where the stylized dataset will be stored (optional, default: `output/`)
  - `--num-styles <N>` number of stylizations to create for each content image (optional, default: `1`)
  - `--alpha <A>` Weight that controls the strength of stylization, should be between 0 and 1 (optional, default: `1`)
  - `--extensions <EX0> <EX1> ...` list of image extensions to scan style and content directory for (optional, default: `png, jpeg, jpg`). Note: this is case sensitive, `--extensions jpg` will not scan for files ending on `.JPG`. Image types must be compatible with PIL's `Image.open()` ([Documentation](https://pillow.readthedocs.io/en/5.1.x/handbook/image-file-formats.html))
  - `--content-size <N>` Minimum size for content images, resulting in scaling of the shorter side of the content image to `N` (optional, default: `0`). Set this to 0 to keep the original image dimensions.
  - `--style-size <N>` Minimum size for style images, resulting in scaling of the shorter side of the style image to `N` (optional, default: `512`). Set this to 0 to keep the original image dimensions (for large style images, this will result in high (GPU) memory consumption).
  - `--crop <N>` Size for the center crop applied to the content image in order to create a squared image (optional, default 0). Setting this to 0 will disable the cropping.

Here is an example call:

```
  python3 stylize.py --content-dir '/Users/vignavramesh/Documents/sample/' --style-dir '/Users/vignavramesh/Downloads/train/' --alpha 1 --content-size 0 --style-size 0
```

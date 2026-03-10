# PROMPT

I want to follow the approach to build HTML tools described in [this article](https://simonwillison.net/2025/Dec/10/html-tools/) by Simon Willison (standalone HTNL page with embedded Javascipt and CSS) to build a photo collage tool.

The workflow is as follows:

## Main screen

In the main screen, user can add:

- a date (powered by a date picker) + a related checkbox to include/exclude the date in the final collage
- a plain text description (multiline) + a related checkbox to include/exclude the description in the final collage
- add image in 2 ways:
  - upload a single image file from the device 
  - upload multiple image files from the device, for a photo collage. The workflow for the photo collage is desccribed in more details below.
- when either a single image or a photo collage is added, a thumbnail of the image/collage will be shown.
- a button to generate the final collage 

When the user clicks on the "generate collage" button, the final collage will be generated: the single image OR the ohoto collage at the top, and the date and description at the bottom (if the related checkbox is checked). A download link will be available to download the generated collage as a single image file.

## Photo collage workflow

When the user uploads multiple image files, they then can choose the layout. There is layout options for 2, 3 and 4 images. See screenshot below for the layout options:

Screenshots showing 2, 3 and 4 images layout options: each one contains icons representing the layout options.

- ![collage - 2 images layout options](/images/collage-2layout.png)
- ![collage - 3 images layout options](/images/collage-3layout.png)
- ![collage - 4 images layout options](/images/collage-4layout.png)
- ![collage - selected image option](/images/collage-imageSelected.png)

- from the 2 and 3 image options, a button will be shown to add one more image and switch to the 3 and 4 image layout options respectively.
  - from the 4 image layout options, this button to add more image will be disabled.
- a preview of the collage will be shown based on the selected layout option.
- user can select the layout option they want by clicking on the related icon. The selected layout will be highlighted and the preview will be updated accordingly.
- when the image original aspect ratio does not fit the layout, the image will be cropped to fit the layout.
- user can drag and drop an image in the collage preview to change the position of the image in the collage.
- user can select an image to apply the following transformations:
  - rotate (90°) with a button
  - zoom in/out (crop the image to fit the layout, but with a zoomed in version of the image) with "+" and "-" buttons
  - move the image within the layout in the preview (when the image is zoomed in and cropped, user can move the image within the layout to select which part of the image will be shown in the collage)
  - delete the image from the collage with a delete button (when the image is deleted, the layout will switch to the one corresponding to the new number of images in the collage)
- at the bottom of that screen there are 2 buttons:
    - Cancel: discard the collage and go back to the main screen
    - Save: save the collage and go back to the main screen, where the generated collage will be shown as a thumbnail.

## General requirements:

- call the HTML file name `photo-collage.html`
- Wherever it makes sense, and to avoid reinventing the wheel, use existing libraries (JS, CSS). Load them from an existing CDN service (e.g. jsdelivr, cdnjs, etc.)
- The result file should be a image with the ratio 3:2.
- date format
    - use `DD MMM YYYY` (e.g. `01 Jan 2025`) on the collage.
    - use international format `DD/MM/YYYY` in the date picker input field.

At the end user can download the generated collage as a single image file with a link.

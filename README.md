# Fine Tuning BLIP on Cityscapes
*UPENN-VIRT-DATA-PT-06-2023-U-LOLC-MTTH Project 4 - Team 3*

## Description
<!--- NEEDS UPDATING --->

## Installation/Instructions
### Requirements
This project is centered around Jupyter Notebooks.
All notebooks generated with this project were originally created on [Google Colaboratory](https://colab.research.google.com).
Loading them into Colab is probably the best way to run them and they have not been tested on individual computers.

### Installation
Clone this repo: `git clone https://github.com/VishnuP02/image_captioner.git`

Loading the notebooks into Google Colaboratory is probably the best way to run them.

### Output
The fundamental output of this project is the fine tuned model weights, which have been exported from notebook `2 Fine_tuning.ipynb`.
This model may be imported into new programs or projects.
As the model is about 1GB, it is being hosted on [Google Drive](https://drive.google.com/drive/folders/1-dF7t6kH-yHUwVBIahOwREUFI6yO46-t?usp=share_link).

Notebook `3 Pres_tuned.ipynb` provides an environment that can load the fine tuned model without conducting any training.
The final cells of this notebook access images from outside of the training set and use the model to generate captions for them.

[screenshots]

## Credits
The base model used for this project was [BLIP](https://huggingface.co/Salesforce/blip-image-captioning-large), an LLM created by Salesforce and accessed through [Hugging Face](https://huggingface.co).

Training images in this project were obtained from Adobe Stock through an Education License and may not be repurposed by third parties. The Education License permits faculty members and staff members to use, reproduce, archive, modify, and display the asset: for advertising, marketing, promotional, and decoration purposes related solely to the Enterprise, for professional and academic activities related solely to the Enterprise, and not for any other commercial purpose. Students may use, reproduce, archive, modify, and display the asset in all media, solely in connection with course work at the Enterprise, and not for any other commercial or paid purposes. The use of these licensed images is therefore intended for the contributors to this educational project, as part of the edX bootcamp in collaboration with the University of Pennsylvania, and may not be used in other ways.

Training images have not been provided in this repository due to their license.

Test images were acquired from various places around the web.
Their URL should be listed in the cells in which they are accessed.
The majority of these images are hosted on [Unsplash](https://unsplash.com).

## License
[License](LICENSE)

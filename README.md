# Fine Tuning BLIP on Cityscapes
*UPENN-VIRT-DATA-PT-06-2023-U-LOLC-MTTH Project 4 - Team 3*

## Project Description
This project attempts to caption various images of cityscapes through the finetuning of the BLIP model.
BLIP, or Bootstrapping Languange-Image Pre-Training, is a pre-training framework for unified vision-language 
understanding and generation. In other words, it is a multi-task model (i.e., multimodal mixture of encoder-decoder)
pre-trained on large-scale image-text datasets that is able to perform tasks including visual question answering, 
image-text answering, and most importantly for this project, image captioning. 

To begin the finetuning process, images of cityscapes of the top 40 cities around the world were gathered from Adobe Stock with
their accompanying titles or descriptions. The gathered dataset was placed in a folder called `project4images` of the Google Drive folder
titled, `BC-Project4`. 

The images and text were preprocessed in `1 Preprocess_csv.ipynb`. This preprocessing entailed the extraction of the image file name, caption, 
and keywords which were saved into a CSV file, "metadata.csv" and placed within the same folder containing the image dataset.

`2 Fine_tuning.ipynb`, as the title suggests, is Google Colaboratory notebook where the finetuning process is undertaken. This process begins with the installation of Hugging Face's transformer library to access pretrained models: 
`!pip install git+https://github.com/huggingface/transformers.git@main`.

An installation of Hugging Face's datasets library for additional data-preprocessing is required:
`!pip install -q datasets`.

Other modules and libraries required for this process is imported in cell 3, before mounting the Google Drive, which facilitates the creation of different file paths, and thus, access to the various folders contained in the Drive. 

The dataset is loaded with the function `load_dataset` which not only allows users to retrieve datasets created by Hugging Face, but also allows users to quickly build datasets of their own: `load_dataset("imagefolder", data_dir=drive_path, split="train")`.

Finally, the processor and model is loaded using the following lines of code:
`processor = AutoProcessor.from_pretrained("Salesforce/blip-image-captioning-base")`
`model = BlipForConditionalGeneration.from_pretrained("Salesforce/blip-image-captioning-base")`. 

With these steps taken, the dataset is processed in a class called `CustomImageDataset`, loaded in, and trained in a custom function. For actual code, please refer to the notebook.

`3 Pres_un_tuned.ipynb` and `3 Pres_tuned.ipynb` showcases the BLIP models ability to caption images before and after the finetuning process. 

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

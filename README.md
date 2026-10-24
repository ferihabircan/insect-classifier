# 🐞 insect-classifier

An image classifier that identifies insects from habitus photos (whole-body pictures), built with fastai and deployed as a Gradio app on Hugging Face Spaces.

## How it works

1. **Data:** the [Insect Identification from Habitus Images](https://www.kaggle.com/datasets/kmldas/insect-identification-from-habitus-images) dataset from Kaggle, with **291 insect classes**.
2. **Preprocessing:** a fastai `DataBlock` with an 80/20 random train/validation split. It uses presizing: images are resized to 460px, then augmented and cropped to 224px in batches.
3. **Model:** a pretrained **ResNet-34** fine-tuned with `vision_learner`. The head is trained first, then the whole network, with `error_rate` as the metric.
4. **Deployment:** the exported model and a Gradio `app.py` are pushed to a Hugging Face Space.

## Run it

The notebook was written for **Google Colab**.

1. Open `Untitled14.ipynb` in Colab (a GPU runtime is recommended).
2. Upload your `kaggle.json` API key when asked, so the dataset can be downloaded.
3. Run the cells in order to train, evaluate and export the model.
4. To deploy, set `hf_username` in the deployment cell to your own Hugging Face username and log in with a Hugging Face token.

`untitled14.py` is the same notebook exported as a Python script.

## Stack

fastai · PyTorch · Gradio · Hugging Face Hub · Kaggle API

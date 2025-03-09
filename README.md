# Faster R-CNN Fine-Tuning  
[![Skills](https://skillicons.dev/icons?i=pytorch,python)](https://skillicons.dev)

This repository contains a Jupyter Notebook designed for fine-tuning a Faster R-CNN model on a custom object detection dataset. Built using **PyTorch**, this notebook provides a straightforward way to fine-tune a pre-trained Faster R-CNN model for your specific detection tasks.

## Overview

This notebook helps users fine-tune a Faster R-CNN model, originally pre-trained on the COCO dataset, to work with their own custom dataset. The process includes:

1. Loading a custom dataset in COCO format.
2. Training the Faster R-CNN model.
3. Evaluating model performance using **mean Average Precision (mAP)**.

Whether you're working with a small dataset or scaling up to a larger collection of images, this notebook will guide you through the fine-tuning process.


## Dataset

The dataset should be in COCO format, with the following structure:

```json
{
  "images": [
    {
      "id": 1,
      "file_name": "/path/to/image1.jpg",  // Full absolute path to the image
      "height": 720,
      "width": 1280
    },
    {
      "id": 2,
      "file_name": "/path/to/image2.jpg",  // Full absolute path to the image
      "height": 720,
      "width": 1280
    }
  ],
  "annotations": [
    {
      "image_id": 1,
      "category_id": 1,
      "bbox": [x_min, y_min, width, height],
      "area": area,
      "iscrowd": 0
    },
    {
      "image_id": 1,
      "category_id": 2,
      "bbox": [x_min, y_min, width, height],
      "area": area,
      "iscrowd": 0
    }
  ],
  "categories": [
    {
      "id": 1,
      "name": "class1"
    },
    {
      "id": 2,
      "name": "class2"
    }
  ]
}

```


### Annotations

- The annotations file must be in JSON format, containing object annotations with bounding box coordinates in `[x_min, y_min, width, height]` format.
- Ensure that class IDs start from 1 (0 is reserved for the background class).
- The absolute path of the images should be specified in the `file_name` field.

## Training and Evaluation

1. Load the dataset and annotations from the specified directories.
2. Fine-tune the Faster R-CNN model using the training data.
3. Evaluate the model on a test set and display metrics such as mAP.

## Notes

- Batch size may need to be adjusted based on the GPU/VRAM capacity.
- If you encounter Colab crashes due to VRAM limitations, reduce the batch size and try again.

## Author

Created by [ady-cf](https://github.com/ady-cf).

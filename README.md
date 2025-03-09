# Faster R-CNN Fine-Tuning

This repository contains a Jupyter Notebook for fine-tuning a Faster R-CNN model on a custom dataset for object detection.

## Overview

This notebook is designed to help users fine-tune a Faster R-CNN model pre-trained on the COCO dataset for their custom object detection tasks. The process involves loading a custom dataset in COCO format, training the Faster R-CNN model, and evaluating its performance using mean Average Precision (mAP).

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

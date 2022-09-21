# Printed Text Recognition

## Welcome

The service receives an image file of the line English printed text and uses it as input for a pre-trained model.

## What’s the point?

The service performs printed text recognition on images using machine learning techniques. The service retrieves the image file and outputs a text string as a result of image recognition.

## Model details:

The service receives an English-language image of a printed text line and uses it as input for a [TrOCR](https://github.com/microsoft/unilm/tree/master/trocr) model based on the Transformer architecture trained on the [SROIE](https://arxiv.org/pdf/2103.10213.pdf) dataset, and outputs the result of image recognition as a text sequence. There are no limitations on the maximum size of the images, as they are scaled up to 384x384 pixels before the input.

## Important information

The service works only with images of printed text lines. If there are several lines of printed text in the input or if the text is handwritten, the service will not work correctly.

## How does it work?

The user must provide the following inputs in order to start the service and get a response:

Inputs:
 -   `method`: printedOCR
 -   `input_path`: Path to '\*.txt' file containing JSON representation of input argument 'file@data' and its value - path to '\*.[image format extension]' input image file.

Example of input file content:

```
{"file@data": "examples/ocr_image.jpg"}
```

## What to expect from this service?

Input image: examples/ocr_image.jpg\
[![imageban](https://i5.imageban.ru/out/2022/08/30/483116767c64a67a517d3b814f66be8a.jpg)](https://imageban.ru)

Response: text: "LICENSEE OF MCDONALD'S"

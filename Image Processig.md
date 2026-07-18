# Image Processing

Image processing is the technique of using computers to **process, analyze, enhance, and manipulate images**. An image is represented as a collection of pixels, and image processing techniques are used to improve the image or extract useful information from it.

For example, when a mobile phone improves a dark photograph, detects a face, or scans a QR code, image processing is being used.

## Basic Definition

> **Image processing is the process of performing operations on an image to enhance its quality or extract meaningful information from it using computer algorithms.**

## Basic Image Processing System

The general steps are:

**Image Acquisition → Pre-processing → Image Enhancement → Segmentation → Feature Extraction → Classification/Recognition**

---

## 1. Image Acquisition

The first step is to obtain an image using an input device such as:

- Digital camera
- Scanner
- CCTV camera
- Medical imaging equipment
- Satellite camera

The captured image is converted into a digital format that a computer can process.

**Example:** An X-ray image captured using an X-ray machine.

---

## 2. Pre-processing

Pre-processing improves the quality of the input image before further processing.

Common operations include:

- Removing noise
- Adjusting brightness
- Correcting contrast
- Resizing the image
- Removing unwanted regions

**Example:** Removing noise from a medical X-ray image.

---

## 3. Image Enhancement

Image enhancement improves the visual appearance of an image.

Techniques include:

- Contrast enhancement
- Brightness adjustment
- Sharpening
- Smoothing
- Histogram equalization

**Example:** Enhancing a dark image to make objects more visible.

---

## 4. Image Restoration

Image restoration attempts to recover an image that has been degraded or damaged.

It can correct:

- Blur
- Noise
- Motion distortion
- Camera defects

**Example:** Removing blur from an old photograph.

---

## 5. Image Segmentation

Image segmentation divides an image into meaningful regions or objects.

For example, in a medical image, segmentation can separate:

**Background → Healthy Tissue → Tumor Region**

Common techniques include:

- Thresholding
- Edge detection
- Region-based segmentation

---

## 6. Feature Extraction

Important characteristics of an image are extracted.

Features may include:

- Shape
- Size
- Colour
- Texture
- Edges

**Example:** In face recognition, features such as the position of the eyes, nose, and mouth are extracted.

---

## 7. Image Classification and Recognition

The image or object is identified based on its extracted features.

Examples:

- Identifying a face
- Recognizing handwritten numbers
- Detecting a tumor
- Identifying vehicles
- Recognizing objects

---

# Types of Images

## 1. Binary Image

A binary image contains only two pixel values:

- `0` → Black
- `1` → White

**Example:** A scanned black-and-white document.

---

## 2. Grayscale Image

A grayscale image contains different shades of gray, usually from:

- `0` → Black
- `255` → White

A grayscale image has only intensity information.

---

## 3. Colour Image

A colour image generally consists of three components:

- Red
- Green
- Blue

This is called the **RGB colour model**.

---

# Common Image Processing Techniques

## 1. Filtering

Filtering is used to remove noise or improve image quality.

- **Low-pass filter:** Removes noise and smooths the image.
- **High-pass filter:** Enhances edges and sharp details.

---

## 2. Edge Detection

Edge detection identifies the boundaries of objects in an image.

Popular methods include:

- Sobel operator
- Prewitt operator
- Canny edge detector

---

## 3. Thresholding

Thresholding converts a grayscale image into a binary image based on a selected intensity value.

For example:

- Pixel value greater than threshold → White
- Pixel value less than threshold → Black

---

## 4. Morphological Processing

Morphological operations process the shape and structure of objects in an image.

Common operations include:

- Erosion
- Dilation
- Opening
- Closing

---

# Applications of Image Processing

Image processing is widely used in the following fields:

## Medical Field

- X-ray analysis
- MRI and CT scan analysis
- Tumor detection
- Cell counting

## Security

- Face recognition
- Fingerprint recognition
- CCTV surveillance

## Industrial Automation

- Defect detection
- Quality inspection
- Robot vision

## Remote Sensing

- Satellite image analysis
- Weather monitoring
- Land classification

## Transportation

- Number plate recognition
- Traffic monitoring
- Self-driving vehicles

## Everyday Applications

- QR code scanning
- Instagram filters
- Face unlock
- Document scanning

---

# Simple Example

Consider a **blurred and dark photograph**:

1. The camera captures the image.
2. Noise is removed.
3. Brightness and contrast are improved.
4. The image is sharpened.
5. Important objects are detected.
6. The objects are classified.

This complete process is called **image processing**.

---

## In One Line

> **Image processing converts a raw image into a better-quality image or useful information.**

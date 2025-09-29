# Plankton Image Analysis

This repository contains a Jupyter Notebook that explores preprocessing, analysis, and classification techniques for plankton images. The work is based on microscopy data of marine plankton, with applications in ecology, marine biology, and automated biodiversity monitoring.

## Dataset

We use plankton imagery from the **WHOI-Plankton Image Dataset**:  
[https://darchive.mblwhoilibrary.org/collections/aad045e7-1fcf-5650-82ee-c62bd604d225](https://darchive.mblwhoilibrary.org/collections/aad045e7-1fcf-5650-82ee-c62bd604d225)  

Please cite this dataset if you use it in your own research or applications.

### Dataset Preview
![Plankton Dataset Preview](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTBSWOs31DphbSg9-xe-AeRAdf5sORIoqvVeg&s)

---

## Notebook Contents

The notebook demonstrates:  
- **Data Loading & Exploration** – how to work with large-scale plankton image datasets.  
- **Preprocessing** – illumination correction, background estimation, noise removal, and contrast normalization to prepare images for downstream tasks.  
- **Basic Analysis** – visualization of plankton samples and preliminary feature extraction for classification.

---

## Future Scope

This project lays the groundwork for more advanced machine learning pipelines in plankton recognition.

### 1. Image Segmentation
- Use instance segmentation models (e.g., **YOLO-Seg, Mask R-CNN, or MaskFormer-lite**) to detect and segment individual plankton from complex microscopy images.  
- Handle multiple organisms per frame by separating merged instances using watershed or contour-based splitting.  
- Apply mask-based filtering to remove debris, noise, or artifacts.

### 2. Embedding-Based Classification
- After segmentation, extract **embedding vectors** for each plankton crop using lightweight backbones (e.g., **MobileNetV3, EfficientNet-lite**).  
- Train embeddings with margin-based losses (ArcFace, CosFace) to achieve strong separation between taxa.  
- Use **prototype-based nearest class mean (NCM)** or **k-NN classifiers** for flexible few-shot classification, enabling incremental addition of new species without retraining the entire model.  
- Implement **open-set recognition** to reject unknown or out-of-distribution samples.

This two-stage pipeline (segmentation + embedding classification) allows robust plankton identification, scalable to real-world deployments in marine research.

---

## Reference: Embedding Models
Below is a conceptual diagram of an embedding-based model architecture (example: **OpenAI CLIP**):

![CLIP Model Diagram](https://miro.medium.com/1*tg7akErlMSyCLQxrMtQIYw.png)

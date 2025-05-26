# Visual Recommendation System

<p align="center">
 <img src="https://yt3.googleusercontent.com/A2PDGXF6Rw73xB0nNNY040ulT4EAXC_dzjDRnrfiY8vpt3LKbaUOD79u6yEAiHf9JIAgM1LGfw=s900-c-k-c0x00ffffff-no-rj" title="book" width="180" />
</p>

This project was developed during the **Machine Learning** training program offered by **DIO (Digital Innovation One)** in partnership with **BairesDev**, specifically within the Deep Learning section.

The main objective of this project is to create a **purely visual item recommendation system**, utilizing neural networks for extracting *embeddings* (vector representations of images).

---

## How It Works (Code Flow)

The system operates by comparing the visual characteristics of items to recommend those that are most similar. The implementation, based on a Python class, follows these steps:

1.  **Recommender Initialization**: The `ImageRecommender` class is initialized with the path to the folder containing the images. An instance of the **VGG16** neural network (pre-trained on ImageNet, without the final classification layers and with average *pooling*) is loaded as the base model.
2.  **Image Loading and Preprocessing**: For each image, it is loaded, resized to `(224, 224)` pixels, converted to a NumPy array, and preprocessed according to VGG16 requirements.
3.  **Feature Extraction**:
    * The `extract_features` method iterates over all images in the specified directory.
    * For each image, *features* (visual characteristics) are extracted using the VGG16 model.
    * The resulting *embedding* vectors are stored in a dictionary, where the key is the image path and the value is the flattened feature vector.
4.  **Getting Recommendations**:
    * Given the path to a query image, its *features* are extracted.
    * **Cosine similarity** is calculated between the query image's *features* and the *features* of all other stored images.
    * Images are then sorted by similarity (from highest to lowest), and the top `N` most similar ones (excluding the query image itself) are returned as recommendations.
5.  **Visualizing Results**: The `visualize_recommendations` method plots the query image next to the recommended images, displaying the similarity value for each.

---

## What Makes It Unique?

This project stands out for its ability to provide **purely visual suggestions**. This means the system does not require additional metadata (such as product descriptions, categories, or user reviews) to find related items. It relies exclusively on the visual resemblance between products, making it ideal for scenarios where textual data is scarce or irrelevant.

---

## Technologies and Libraries Used

* **Python**: Main programming language.
* **TensorFlow / Keras**: For building and utilizing the VGG16 neural network and other Deep Learning operations.
* **NumPy**: Essential for efficient array manipulation and numerical operations with *embeddings*.
* **Matplotlib**: For creating detailed graphs and visualizations of the results.
* **scikit-learn**: Specifically for `cosine_similarity` calculation.
* **PIL (Pillow)**: For image manipulation and loading.
* **os**: For file system operations, such as listing directories.

---

## How to Run the Project

To set up and run this project locally, follow these steps:

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/phaa/dl-recommendation-system.git
    cd dl-recommendation-system
    ```

2.  **Create a virtual environment (recommended)**:
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
    *Note: Ensure that the `requirements.txt` file exists in the project root and lists all necessary Python dependencies (e.g., `tensorflow`, `numpy`, `matplotlib`, `scikit-learn`, `Pillow`).*

4.  **Prepare the Image Dataset**:
    * Create a folder named `watches` (or your preferred name) in the project root.
    * Place your watch images (or other items) inside this folder. The code expects the images to be in this directory.

5.  **Execute the notebook**:

---

## Example Results

Here is an example of the best results obtained after a search, demonstrating the visually similar recommendations:

<p align="center">
 <img src="https://github.com/phaa/dl-recommendation-system/blob/main/Captura%20de%20tela%20de%202025-04-08%2022-45-55.png" alt="Example Recommendation Results" width="800" />
</p>

---

## Future Improvements

* Integrate with a real database for persistent storage of *embeddings* and image metadata.
* Develop a web interface or API for system interaction, allowing users to upload query images.
* Explore the use of other pre-trained models (e.g., ResNet, Inception) or more advanced neural network architectures for feature extraction.
* Implement a caching mechanism for frequently queried *embeddings* to optimize performance.
* Evaluate system performance using quantitative recommendation metrics, such as precision and recall, on a test set.
* Add functionality to handle large volumes of image data more efficiently (e.g., batch processing).
  
---

## Author

[Pedro Azevedo](https://www.linkedin.com/in/pedrohazevedo/)

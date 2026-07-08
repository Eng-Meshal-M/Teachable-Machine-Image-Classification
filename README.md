# 🖼️ Image Classification with Google Teachable Machine

> **Developed by:** Meshal Talal Al Mehmady

---

## 📌 Project Overview

This project demonstrates how to build a simple image classification model using **Google Teachable Machine**. The model is trained using multiple image classes, exported in **TensorFlow (Keras)** format, and integrated into a Python script to classify new input images.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c13a2042-6210-45e4-936b-8e38688e9931" width="85%" />
</p>

---

## 📂 Project Structure

```text
Teachable-Machine-Image-Classification/
│
├── model/
│   ├── keras_model.h5
│   └── labels.txt
│
├── test_images/
│   └── test_image.jpg
│
├── predict.py
└── README.md
```

---

## 🚀 Step 1 — Create a New Project

Open **Google Teachable Machine** and create a new **Image Project** using the **Standard Image Model**.

This project type allows you to train an image classification model without writing the training code manually.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d90e4d56-c195-4c2e-a089-85341cd32df9" width="85%" />
</p>

---

## 🖼️ Step 2 — Create Image Classes

Create at least **two image classes**.

For each class, upload several training images. Using images captured from different angles, backgrounds, and lighting conditions helps improve the model's performance.

Example:

- Class 1
- Class 2
- Class 3 *(Optional)*

<p align="center">
  <img src="https://github.com/user-attachments/assets/c6a51738-2652-408a-9fab-5dd00fd1f4bc" width="85%" />
</p>

---

## 📤 Step 3 — Upload Training Images

Upload the images into their corresponding classes.

The quality and variety of the training images have a direct impact on the prediction accuracy.

After uploading all images, verify that every class contains the correct dataset before training.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c857c90d-15c6-4878-bc76-2d43eb7f0161" width="85%" />
</p>

---

## 🧠 Step 4 — Train the Model

Click **Train Model** and wait until the training process is completed.

Once the model is trained, test it using different images directly inside Teachable Machine to verify that it correctly recognizes each class.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a1c20519-c37f-46c6-9178-6a8097537590" width="85%" />
</p>

---

## 📦 Step 5 — Export the Model

After training, export the model by selecting:

```text
TensorFlow
    ↓
Keras
```

Download the exported model files:

- `keras_model.h5`
- `labels.txt`

Then, open the **Code** tab in the export window and copy the generated Python code.

This code will be pasted into your **Google Colab** notebook and modified in the next step to work with the exported model.

<p align="center">
  <img src="https://github.com/user-attachments/assets/613c710e-3b7a-4f0f-af61-cf04660f8989" width="85%" />
</p>

---

## 💻 Step 6 — Open Google Colab

Create a new notebook in **Google Colab**.

Upload the exported model files and the test image:

- `keras_model.h5`
- `labels.txt`
- Test image

After uploading the files, the notebook is ready for the next step.

<p align="center">
  <img src="https://github.com/user-attachments/assets/83bc95b3-1479-42cb-bfd1-e699c67eec3b" width="85%" />
</p>

---

## 📝 Step 7 — Update the Python Script

After pasting the generated code into **Google Colab**, make the necessary modifications before running it.

### 1. Load the exported model

Replace the original model loading code with:

```python
import tf_keras as tk

model = tk.models.load_model("keras_model.h5")
```

Make sure the filename exactly matches the exported model file.

For example, if the exported file is named `keras_model.h5`, do **not** use `Keras_Model.h5` or any other variation in capitalization. The filename in the code must match the actual filename exactly.

### 2. Update the input image path

Locate the following line:

```python
image = Image.open("<IMAGE_PATH>").convert("RGB")
```

Replace `<IMAGE_PATH>` with the name of your uploaded test image.

For example:

```python
image = Image.open("Cat.jpg").convert("RGB")
```

This allows the script to load the correct image for prediction.

---

## ⚙️ Step 8 — Run the Prediction Script

Run the Python script to load the trained model and classify a new image.

The script performs the following tasks:

- Loads the trained model.
- Reads the class labels.
- Loads the input image.
- Resizes and preprocesses the image.
- Predicts the image class.
- Displays the confidence score.

Example:

```text
1/1 [==============================] - 1s 780ms/step
Class: Cat
Confidence Score: 0.9999106
```
---

## 📊 Step 9 — Model Evaluation

The trained model was evaluated using images that were **not included during training**.

The prediction confidence remained consistently high across the testing images, indicating that the model successfully learned the visual differences between the classes.

<p align="center">
  <img src="https://github.com/user-attachments/assets/30bb773b-1d14-4c77-b82e-bea6853a4559" width="46%" />
  <img src="https://github.com/user-attachments/assets/86d54dbb-a593-40ee-ba0e-f3097b1fbda5" width="46%" />
</p>

---

## 🛠️ Technologies Used

- Google Teachable Machine
- TensorFlow
- Keras
- Python
- Google Colab

---

## ✨ Future Improvements

- Increase the dataset size.
- Add more image classes.
- Improve prediction accuracy.
- Build a simple graphical interface.
- Deploy the model as a web application.

---

## 📚 References

- Google Teachable Machine
- TensorFlow Documentation
- Google Colab Documentation

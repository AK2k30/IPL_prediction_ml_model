# IPL Score Predictor 2022

<div style="display: flex; justify-content: center;">
    <img src="https://github.com/user-attachments/assets/4f549d42-4cbc-494b-9049-72cac8886f02" alt="Screenshot 1" style="width: 45%; margin-right: 10px;"/>
    <img src="https://github.com/user-attachments/assets/47c0c3aa-7980-4eec-a1c0-0ee776229189" alt="Screenshot 2" style="width: 45%;"/>
</div>

## Project Overview

The IPL Score Predictor is a machine learning model built to predict the scores of IPL matches in real-time. This Streamlit-based web application allows users to input ongoing match details such as the batting team, bowling team, current runs, overs, and wickets to predict the final match score.

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Project Structure](#project-structure)
5. [Model Details](#model-details)
6. [Contributing](#contributing)
7. [License](#license)

## Features

- **User-Friendly Interface:** Easy to use with dropdowns and sliders for input.
- **Real-Time Prediction:** Provides real-time score predictions based on current match conditions.
- **Background Image:** Visually appealing with a background image.
- **Error Handling:** Ensures valid input data for accurate predictions.

## Installation

### Prerequisites

Ensure you have the following installed:

- Python 3.7 or higher
- Streamlit
- NumPy
- Scikit-Learn
- Gdown (for downloading model from Google Drive)

### Steps

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/your_username/ipl_score_predictor.git
    cd ipl_score_predictor
    ```

2. **Create a Virtual Environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install Dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Download the Model File:**

    The model file should be in a `model` directory within your project. If you don't have it, download it from the provided Google Drive link and place it in the `model` directory.

    ```bash
    mkdir model
    # Download the model file from the Google Drive link and place it in the `model` directory
    ```

## Usage

1. **Run the Streamlit App:**

    ```bash
    streamlit run streamlit_app.py
    ```

2. **Interact with the App:**

    - Open your web browser and go to `http://localhost:8501`
    - Select the batting and bowling teams
    - Input the current match details (runs, overs, wickets, etc.)
    - Click the "Predict Score" button to get the predicted score range

## Project Structure

```
ipl_score_predictor/
│
├── model/
│ └── ml_model.pkl # Pre-trained machine learning model
│
├── app.py # Main Streamlit app script
|
├── ipl_data.csv # Data csv file
│
├── requirements.txt # Required Python packages
│
└── README.md # Project README file
```

## Model Details

- **Model Type:** Random Forest Regressor (or any other model used)
- **Training Data:** Historical IPL match data
- **Features Used:** Batting team, bowling team, current runs, current overs, wickets fallen, runs in last 5 overs, wickets in last 5 overs

### Loading the Model

The model is loaded using the `pickle` library in Python. The model file (`ml_model.pkl`) should be placed in the `model` directory within the project.

```python
import pickle
import os

model_path = os.path.join(os.path.dirname(__file__), 'model', 'ml_model.pkl')

with open(model_path, 'rb') as file:
    model = pickle.load(file)
```

## Contributing

### Contributions are welcome! Please follow these steps:

1. Fork the repository.

2. Create a new branch (git checkout -b feature-branch).

3. Commit your changes (git commit -m 'Add new feature').

4. Push to the branch (git push origin feature-branch).

5. Open a pull request.

## License

This project is licensed under the MIT License.

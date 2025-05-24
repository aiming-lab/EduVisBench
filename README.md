# EduVisBench

This project conducts a detailed evaluation of webpage images within EduVisBench, providing results on the performance of webpages in educational visualization.

## Prerequisites

1.  **OpenAI Python Package**: Install the required package:
    ```bash
    pip install openai
    ```
2.  **OpenAI API Key**: You must set your OpenAI API key as an environment variable. In your terminal, run:
    ```bash
    export OPENAI_API_KEY="your_actual_api_key_here"
    ```
    Replace `"your_actual_api_key_here"` with your actual API key.

## Directory Structure

For the script to work correctly, your files should be organized as follows, relative to the `run_evaluation.py` script:

```
EduVisBench/       <-- Your main project folder
├── run_evaluation.py          # The main evaluation script
|
├── data.json                    # JSON file containing all questions
│                                # Each question object must have an "id" and a "question" field.
│                                # - If "question" is a path (e.g., "image/my_q_image.png"),
│                                #   it's treated as an image question. The path should be
│                                #   relative to this Edu_visualization_benchmark/ folder.
│                                # - Otherwise, "question" is treated as text.
|
├── data/                          # Directory containing answer images, organized by question ID
│   ├── {question_id_1}/           # Folder named with the exact ID from data.json
│   │   ├── answer_image_A.png
│   │   ├── answer_image_B.jpg
│   │   └── ... (any number of answer images for this question ID)
│   │
│   ├── {question_id_2}/           # Folder for another question ID
│   │   └── single_answer_image.png
│   │
│   └── ... (other question ID folders)
|
└── README.md                    # This file (ensure filename is README.md)
```


## Running the Evaluation Script

1.  Navigate to the `EduVisBench` directory in your terminal:
    ```bash
    cd path/to/your/EduVisBench
    ```
2.  Ensure your `OPENAI_API_KEY` environment variable is set (see Prerequisites).
3.  Run the script:
    ```bash
    python run_evaluation.py
    ```
4.  **Output**: The script will generate a JSON file named `evaluation.json` (by default) in the same directory. This file will contain the detailed evaluation results for each question.

    You can specify a different output file name or path using the `--output_file` argument:
    ```bash
    python run_evaluation.py --output_file my_custom_results.json
    ```
    If you provide a relative path, it will be relative to the script's directory. If you provide an absolute path, that will be used directly.


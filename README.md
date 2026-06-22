 Investigating the Impact of Forest Size on Random Forest Accuracy

Welcome to the Random Forest Tutorial repository! This hands-on, step-by-step project explores how changing the forest size (the number of decision trees, N) affects classification performance.

For this experiment, I utilised the classic Breast Cancer Wisconsin Diagnostic Dataset to train and test several Random Forest models. The primary goal is to find the exact point where adding more trees stops improving diagnostic accuracy and starts wasting computational resources.

Project Structure

random-forest-tutorial/
|-- README.md          # Project overview, installation, and how-to-run guide
|-- requirements.txt   # Text file listing exact library dependencies
|
|-- notebooks/
|   `-- Random_Forest_Tree_Analysis.ipynb  # Your fully executed Jupyter Notebook
|
|-- reports/
|   `-- Random_Forest.pdf     # The compiled PDF version of this report.

Theoretical Quick-View

Instead of relying on a single decision tree—which is prone to overfitting and capturing random noise—the Random Forest algorithm combines multiple decision trees using Bootstrap Aggregation (Bagging) and Feature Subspace Sampling (Breiman, 2001).

Key Mathematics:

The Out-of-Bag (OOB) Constant (36.8%): On average, each individual tree is trained on roughly 63.2%$ of the dataset, leaving about 36.8% of the rows out. These left-out rows are called OOB samples, 

Gini Impurity (G): Used to decide the best split boundaries by measuring how "impure" the data split.

How to Set Up and Run the Project

Follow these steps to set up the project on your local machine:

1. Clone the Repository

Open your terminal or command prompt and run:

git clone [https://github.com/nazeerbaba4786-beep/random-forest-tutorial.git](https://github.com/nazeerbaba4786-beep/random-forest-tutorial.git)
cd random-forest-tutorial


2. Set Up a Virtual Environment (Recommended)

Creating a virtual environment ensures that the project packages don't interfere with your global Python setup.

On macOS/Linux:

python3 -m venv venv
source venv/bin/activate


On Windows:

python -m venv venv
venv\Scripts\activate


3. Install Dependencies

Install all the required Python libraries using the requirements.txt file:

pip install -r requirements.txt


4. Run the Jupyter Notebook

Start the Jupyter interface to view and execute the analysis code:

jupyter notebook notebooks/Random_Forest_Tree_Analysis.ipynb


Core Dependencies (requirements.txt)

The project runs on standard scientific Python libraries:

pandas>=1.3.0 (for dataset exploration and data quality checks)

numpy>=1.20.0 (for numerical processing)

matplotlib>=3.4.0 (for colour-blind friendly visual plots)

scikit-learn>=1.0.0 (for building the Random Forest Classifier)

Summary of Results

Peak Accuracy: The model starts at 95.61% with just 10 trees, climbs to 96.49% at 50 trees, and remains completely flat at 96.49% all the way up to 500 trees.

Key Finding: Scaling beyond 50 trees provides zero additional accuracy gains for this clinical dataset while consuming more CPU memory.

Top Predictor: worst area (importance score: ~0.154) was identified as the most critical geometric indicator for tumour malignancy.

Inclusive & Accessible Design

This project is built to align with academic and accessibility best practices:

Colour-Blind Friendliness: All generated figures (accuracy plots, feature importances, and confusion matrices) are styled using high-contrast grayscale and monochrome formatting, making them fully legible for users with colour vision deficiencies.

Screen Reader Alternatives: Text-based breakdowns of the core workflow pipeline and chart data points are fully detailed inside the main report.
 
# Python Manual CI – Stage 1

## Overview
This repository demonstrates **manual Continuous Integration (CI)**.  
You will learn how to fork, clone, set up a virtual environment, run tests, and push changes without automated CI tools like GitHub Actions.  

---

## Project Structure

python-ci-manual/
│
├── app/
│ └── calculator.py
├── tests/
│ └── test_calculator.py
├── requirements.txt
└── README.md


---

## Step 1 – Fork the Repository

Go to the instructor's repository:

https://github.com/ronelkayam/python-ci-manual


Click **Fork** (top-right corner).  
Now you have a personal copy under your GitHub account.

> This is the repository you will work on and push changes to.

### Option B – Using GitHub CLI

You can also use GitHub CLI to fork the repository without opening a browser:

# Authenticate with GitHub CLI
gh auth login

# Fork the repository and clone it immediately
gh repo fork ronelkayam/python-ci-manual --clone=true
Enter the repository folder:

bash
cd python-ci-manual

###Step 2 – Clone the Repository (if not using CLI)
If you forked the repository through the browser, clone it locally:

Go to your fork on GitHub.

Click Code → HTTPS.

Run in terminal:

bash
git clone https://github.com/ronelkayam/python-ci-manual
cd python-ci-manual
Always work from the project folder (cd python-ci-manual).

###Step 3 – Create a Virtual Environment
Create an isolated environment for project dependencies:

bash
# Create a virtual environment named venv
python -m venv venv

# Activate the environment
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

# Install project dependencies
pip install -r requirements.txt

###Step 4 – Run Tests
Run the tests to ensure the code works:

bash
pytest

Expected output:
3 passed in 0.02s

###Step 5 – Optional: Run the Code Manually
You can also test the functions interactively:


from app.calculator import add, divide

print(add(2, 3))       # Expected: 5
print(divide(10, 2))   # Expected: 5.0

###Step 6 – Commit and Push
After making changes or adding tests, update your repository:

bash
git add .
git commit -m "Example change"
git push origin main
Note: Since there is no automated CI yet, forgetting to run pytest may push bugs to main.

Summary
This stage demonstrates manual CI.

You are responsible for running tests before pushing changes.

In the next stage, we will introduce GitHub Actions for automatic CI.


## About Pytest

[Pytest](https://docs.pytest.org/) is a popular testing framework for Python.  
It automatically discovers and runs tests in your project. By convention, it looks for:

- Files starting with `test_` or ending with `_test.py`
- Functions and classes starting with `test_`

Running `pytest` in the project folder will execute all tests under these files and report any failures.  
This helps ensure your code works correctly before committing or deploying changes.



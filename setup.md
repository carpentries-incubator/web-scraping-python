---
title: Setup
---

In this workshop, you’ll learn how to extract data from websites using Python — a process known as web scraping.

Episode 1 begins with an introduction to how websites are structured using HTML.
You’ll learn how to explore this structure using your browser and how to extract information from it using the `BeautifulSoup` package.

In Episode 2, you’ll learn how to retrieve the HTML of a webpage using the `requests` package and continue practicing how to parse and extract specific content with `BeautifulSoup`.

Toward the end of the workshop, in Episode 3, we’ll explore the difference between static and dynamic webpages, and how to scrape dynamic content using `Selenium`.

This workshop is intended for learners who already have a basic understanding of Python. In particular, you should be comfortable with:

- Install and import packages and modules
- Use lists and dictionaries
- Use conditional statements (`if`, `else`, `elif`)
- Use `for` loops
- Calling functions, understanding parameters/arguments and return values

## Software Setup

Steps:

1. If you already have Anaconda, Jupyter Lab or Jupyter Notebooks installed in your computer, skip to step 2. Follow Miniforge's [download](https://github.com/conda-forge/miniforge?tab=readme-ov-file#download) and [installation](https://github.com/conda-forge/miniforge?tab=readme-ov-file#install) instructions for your respective operating system. If you are using a Windows machine, make sure you mark the option to "Add Miniforge3 to my PATH environment variable".
2. If you are using Mac or Linux, open the 'Terminal'. If you are using Windows, open the 'Command Prompt' or 'Miniforge Prompt'.
3. Activate the base conda environment by typing and running the code below to activate your environment.

```terminal
conda activate
```

4. Install the necessary packages by running:
```terminal
pip install requests beautifulsoup4 selenium webdriver-manager pandas tqdm jupyterlab
```

5. Start Jupyter Lab by running: 
```terminal
jupyter lab
```

6. In a new Jupyter Notebook run the following code in a cell to check the necessary libraries can be loaded:
```python
from bs4 import BeautifulSoup
import requests
from selenium import webdriver
from selenium.webdriver.common.by import By
import pandas as pd
```

## Additional resources
- Mitchell, R. (Ryan E. ). (2024). Web scraping with Python : data extraction from the modern web (3rd edition.). O’Reilly Media, Inc.
- Chapagain, A. (2023). Hands-On Web Scraping with Python : Extract Quality Data from the Web Using Effective Python Techniques (Second edition.). Packt Publishing.

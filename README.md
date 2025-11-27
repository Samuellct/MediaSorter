<h1 align="center">MediaSorter</h1>

[![Python 3.11.9](https://img.shields.io/badge/Python-3.11.9-blue.svg)](https://www.python.org/downloads/release/python-3119/)
[![Project Status](https://img.shields.io/badge/Status-Working-brightgreen.svg)]()

## 🌟 Quick overview

This project is a **Jupyter Notebook-based Python script** designed to analyze and organize local media folders (movies and TV series).

It scans file and folder names (e.g. `Title.Year.H265.mkv`), extracts the title and year and uses an external API to fetch detailed metadata. The script includes basic cleaning logic to handle common file naming conventions (dots, tags, quality indicators).

The primary goal is to **group media items** based on common characteristics:

* **Grouped by Saga/Collection** (e.g., all films in the "Harry Potter Collection").
* **Grouped by Director** (films sharing the same director, excluding those already in a saga).
* Media items that cannot be identified reliably are flagged for **Manual Check**.

## 🔑 Dependencies

<p align="center">
  <img src="https://www.themoviedb.org/assets/2/v4/logos/v2/blue_long_1-8ba2ac31f354005783fab473602c34c3f4fd207150182061e425d366e4f34596.svg" alt="TMDb Logo" width="300"/>
</p>

This project relies entirely on **The Movie Database (TMDb)** for all media data.

| Component | Detail |
| :--- | :--- |
| **API Used** | TMDb (The Movie Database) |
| **Python Package** | **tmdbsimple** by [celiao](https://github.com/celiao) |

## 🚀 Getting Started

### Prerequisites

1.  **Install Python** (3.11.9 or newer recommended).
2.  **Install Dependencies:**
    ```bash
    pip install tmdbsimple pandas tqdm
    ```
3.  **Get a TMDb API Key:** You must register for a free account and obtain an **API Read Access Token** from the [TMDb website](https://www.themoviedb.org/documentation/api).

### Usage

1.  Open the script in your Jupyter Notebook environment.
2.  **Configuration (Initial Cell):**
    * Replace `'YOUR_TMDB_API_KEY_HERE'` with your actual TMDb API key:
        ```python
        tmdb.API_KEY = 'YOUR_TMDB_API_KEY_HERE' 
        ```
    * Set the path to the folder you want to scan:
        ```python
        TARGET_FOLDER_PATH = r"C:\Your\Media\Folder" 
        ```
3.  Run the cells sequentially. The script will output five clear sections :
    * **Manual Check:** Items that need renaming or manual searching.
    * **TV Series:** List of identified TV shows.
    * **Grouped by Saga:** Franchises with multiple films.
    * **Grouped by Director:** Directors with multiple non-saga films.
    * **Raw Analysis Details:** The complete table of results.

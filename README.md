# Docify

Docify, a Python-based app, akin to Google Docs, employs sockets for real-time data synchronization, fostering seamless collaboration among users for efficient and concurrent document editing.

## Tech Stacks Used

PyQt5, Sockets, Supabase

## Table of Contents
- [Supabase Tables](#supabase-tables)
- [Configuration](#configuration)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)

## Supabase Tables

### `user` Table
- **Columns:**
  - `uid` (UUID): Unique identifier for the user.
  - `full_name` (Text): Full name of the user.
  - `email` (Text): Email address of the user.
  - `password` (Text): Password of the user.
  - `docs` (Text Array): Array of document IDs associated with the user.

### `docs` Table
- **Columns:**
  - `doc_id` (UUID): Unique identifier for the document.
  - `name` (Text): Name of the document.
  - `links` (Text): Links related to the document.
  - `access` (Text): Access level for the document (e.g., "Restricted", "Readable", "Writable").
  - `user_access` (Text Array): Array of access types for specific users.
  - `content` (Text): Content of the document.
  - `users` (Text Array): Array of user IDs who have access to the document.

## Configuration

1. **Cloudinary Credentials:**
   - Create a file named `cloudinary_credentials.py` in your home directory and configure it with your Cloudinary credentials.
   ```python
   # cloudinary_credentials.py
   import cloudinary
   import cloudinary.uploader

   # Configure your Cloudinary credentials
   cloudinary.config(
     cloud_name='your_cloud_name',  # Replace with your Cloudinary cloud name
     api_key='your_api_key',        # Replace with your Cloudinary API key
     api_secret='your_api_secret'   # Replace with your Cloudinary API secret
   )

2.  **Supabase and SMTP Credentials:**
    - Create a file named `credentials.py` in the utils directory and configure it with your Supabase URL and key, and SMTP username and password.
    ```python
    # utils/credentials.py

    # Supabase credentials
    SUPABASE_URL = 'your_supabase_url'  # Replace with your Supabase URL
    SUPABASE_KEY = 'your_supabase_key'  # Replace with your Supabase API key

    # Google SMTP credentials
    google_username = 'your_smtp_username'  # Replace with your SMTP username
    google_password = 'your_smtp_password'  # Replace with your SMTP password

## Setup Instructions

### Clone the Repository:

    ```bash
    git clone https://github.com/Pudi-Sravan/Docify-TDoC.git
    ```

    ```bash
    cd your-repo-name 
    ```

### Install Dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## To start the main application:

    ```bash
    python3 main.py
    ```

    ```bash
    python3 server.py
    ```

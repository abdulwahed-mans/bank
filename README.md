# Bank ETL Pipeline

This Python script extracts data from the [Universities API](http://universities.hipolabs.com), transforms it, and loads it into a SQLite database.

## Prerequisites

Before running the script, make sure you have Python installed on your system. You'll also need to install the required Python packages:

```bash
pip install requests pandas sqlalchemy
```

## Installation

To install the script, clone the repository from GitHub:

```bash
git clone https://github.com/abdulwahed-mans/bank.git
```

## Usage

To run the script, navigate to the project directory and run the following command:

```bash
python etl_script.py
```

The script will extract data from the Universities API, transform it, and load it into a SQLite database. The database file will be created in the project directory.

## Functionality

The ETL pipeline consists of the following steps:

1. Extract data from the Universities API.
2. Transform the data by selecting specific columns and renaming them.
3. Load the transformed data into a SQLite database.

The script uses the `requests` library to make a GET request to the API and retrieve the data. It then uses the `pandas` library to transform the data by selecting specific columns and renaming them. Finally, it uses the `sqlalchemy` library to load the transformed data into a SQLite database.

## Running the Script in a Docker Container

To run the script in a Docker container, follow these steps:

Build the Docker image:

docker build -t bank .

Run the Docker container:

docker run -it --rm -v $(pwd):/app bank

This will mount the current directory to the /app directory in the container and run the script.

## Running the Script in a Docker Container with a Volume

To run the script in a Docker container with a volume, follow these steps:

Create a volume:

docker volume create bank

Run the Docker container with the volume:

docker run -it --rm -v bank:/app bank

This will create a volume named bank and mount it to the /app directory in the container.

## Running the Script in a Docker Container with a Bind Mount

To run the script in a Docker container with a bind mount, follow these steps:

Run the Docker container with a bind mount:

docker run -it --rm -v $(pwd):/app bank

This will mount the current directory to the /app directory in the container.

## Running the Script in a Docker Container with a Bind Mount and a Volume

To run the script in a Docker container with a bind mount and a volume, follow these steps:

Create a volume:

docker volume create bank

Run the Docker container with a bind mount and a volume:

docker run -it --rm -v $(pwd):/app -v bank:/app bank

This will mount the current directory to the /app directory in the container and create a volume named bank. The data will be stored in the volume.

## License

```plaintext
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

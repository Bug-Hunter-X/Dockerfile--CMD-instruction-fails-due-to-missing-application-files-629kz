# Dockerfile Bug: Missing Application Files

This repository demonstrates a common error in Dockerfiles: forgetting to copy the necessary application files into the image before attempting to execute them.

The original `Dockerfile` attempts to run a Python script (`my_script.py`), but this script is not included in the image.  This results in a runtime error.

The solution provides a corrected Dockerfile that correctly copies the necessary files.

## Bug Reproduction

1.  Clone this repository.
2.  Build the original Dockerfile: `docker build -t missing-files .`
3.  Attempt to run the container: `docker run missing-files` (This will fail).

## Solution

The solution adds a `COPY` instruction to copy the `my_script.py` file into the image before executing it.
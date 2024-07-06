# Specify the base image (replace with your desired Python version)
FROM python:3.11.4

# Create a working directory within the container
WORKDIR /app

# Copy your Python file to the working directory
COPY requirements.txt .
RUN pip install -r requirements.txt  


# Copy your Python file to the working directory
COPY gradio_app.py .
EXPOSE 7860
# Set the command to execute your Python file
CMD ["python", "gradio_app.py"]

#images=[front2]


FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app/devops

# Install Python and pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# Install required Python packages using the --break-system-packages flag
RUN pip install --break-system-packages -r requirements.txt

ENTRYPOINT ["python3"]
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]

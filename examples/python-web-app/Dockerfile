FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

# Set the environment variable to allow pip to break system packages
ENV PIP_BREAK_SYSTEM_PACKAGES=1

# Install Python and pip, then install requirements
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]

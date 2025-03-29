# Python image version
FROM python:3.13.2-alpine

# Install system dependencies
RUN apk -U upgrade

COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# Add to pythonpath the modules which are necessaries
# For examplo: ENV PYTHONPATH="${PYTHONPATH}:/business:/entities:/infrastructure:/job"
ENV PYTHONPATH="${PYTHONPATH}"

# Port to expose
# For example: EXPOSE 8080
EXPOSE 80

# Indicate Workdir and destination application files
# For example: 
# WORKDIR /app/src 
# COPY /src /app/src

WORKDIR /

# add user non-root with user id=6161 non-password gecos empty file in the /etc/passwd file on Unix appuser username and permissions only to read /app
# For example: 
# RUN adduser -u 6161 --disabled-password --gecos "" appuser && chown -R appuser /app
# USER appuser
RUN adduser -u 6161 --disabled-password --gecos "" appuser && chown -R appuser /app
USER appuser

# Launch python startup script
# For example: 
# CMD python job/startup.py
CMD python file.py
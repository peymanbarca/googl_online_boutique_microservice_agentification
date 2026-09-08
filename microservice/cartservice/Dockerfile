FROM python:3.11-slim

WORKDIR /app
COPY ./cartservice/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY ./cartservice ./project/cartservice
COPY shared ./project/shared

EXPOSE 5054
EXPOSE 6054
CMD ["python3", "-m", "project.cartservice.cartservice"]
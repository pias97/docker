FROM python:3.9 as build

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops

FROM python:3.9-alpine

WORKDIR /app

#COPY --from=builder /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages
#COPY --from=builder /app .

COPY --from=build /app /app



CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]





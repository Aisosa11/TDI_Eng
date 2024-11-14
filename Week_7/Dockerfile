#FROM node:12

#WORKDIR /app

#COPY requirements.txt .env
#RUN pip install -r requirements.txt
#RUN npm install

#COPY . .

#CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]`


#FROM python:3.8

#WORKDIR /Week_7


#COPY api/ src/ .env /

#RUN pip3 install --upgrade pip && pip install --no-cache-dir -r api/requirements.txt
#EXPOSE 8080

#CMD ["gunicorn", "application:app", "-b", "0.0.0.0:5000", "-w", "4"]




FROM python:3.10

WORKDIR /Week_7

#COPY api/ src/ .env requirements.txt /
COPY . .
RUN python -m pip install --upgrade pip && pip install --no-cache-dir -r requirements.txt 
#RUN pip install -r requirements.txt

EXPOSE 8000

#CMD ["uvicorn", "main:app", "0.0.0.0:5000", "-w", "4"]
CMD ["uvicorn", "api.main:app", "--host", "0.0.0.0", "--port", "8000"]

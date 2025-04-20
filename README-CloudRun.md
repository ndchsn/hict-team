DEPLOY CODINGAN KE CLOUD RUN
1. Buka Cloud Shell > Pasti sudah masuk ke dalam Open Editor dan Open Terminal
2. Pastikan codingan ada di dalam cloud shell
3. Open Terminal > cd <direktori-folder-codingan>
   - buat file Dockerfile dengan isi script nya > save:
     
     FROM python:3.9-slim
      
     WORKDIR /app
      
     COPY requirements.txt /app/requirements.txt
     COPY . /app
      
     RUN pip install --no-cache-dir -r requirements.txt
      
     EXPOSE 8080
      
     CMD ["python", "app.py"]

   - docker build -t gcr.io/mlpt-cloudteam-migration/flask-app .
   - docker push gcr.io/mlpt-cloudteam-migration/flask-app
   - gcloud run deploy flask-app   --image gcr.io/mlpt-cloudteam-migration/flask-app   --platform managed   --region asia-southeast2   --allow-unauthenticated
   - [Nanti akan muncul url dari cloud Run]
     
4. Kalau ada error di codingan dan ingin push ulang
   - gcloud builds submit --tag gcr.io/mlpt-cloudteam-migration/flask-app
   - gcloud run deploy flask-app   --image gcr.io/mlpt-cloudteam-migration/flask-app   --platform managed   --region asia-southeast2   --allow-unauthenticated
   - [Nanti akan muncul url dari cloud run]
  
5. Update repository
   - gcloud builds submit --tag gcr.io/mlpt-cloudteam-migration/hict-team
   - gcloud run deploy hict-team   --image gcr.io/mlpt-cloudteam-migration/hict-team   --platform managed   --region asia-southeast2   --allow-unauthenticated
   - [Nanti akan muncul url dari cloud run]

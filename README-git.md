Push di Github:
1. <buka git, arahkan ke direktori path file codingan (misal D:/team)>
   - git init
   - <buat file .gitignore, isi dengan ini>:
      __pycache__/
      *.pyc
      .env
      *.log
      .DS_Store
      venv/  [kalau ada folder virtualenv, pastikan foldernya di ignore]
    - git add .
    - git commit -m "message"
  
2. Buat repository baru di GitHub
   - name: hict-team
   - visibility: Public
   - Initialize this repository with a README: NO

3. Hubungkan git lokal ke GitHub
   - git remote add origin https://github.com/ndchsn/hict-team.git
   - git branch -M main
   - git push -u origin main

4. Kalau ada update codingan
   - git add .
   - git commit -m "update message"
   - git pull origin main --rebase
   - git push origin main
   - [PASTIKAN DIREKTORI PATH SELALU DI FOLDER CODINGAN]
  
OPTIONAL
5. Mengecek status remote / lokasi path direktori github di git lokal
   - git remote -v

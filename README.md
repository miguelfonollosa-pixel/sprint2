# 1. Docker Compose: WordPress + MariaDB

Este es la configuracio del wordpress i mariadb, aqui el que posem el que configurem es els usuaris que tindran mariadb i wordpress, i tmb molt important per quins ports podrem entrar al wordpress.

<img width="677" height="786" alt="image" src="https://github.com/user-attachments/assets/38dc0588-c5b9-4ddc-83d2-c2a5de86e249" />

Despres de configurar el contenedor los tindrem que arrancar amb la comanda `docker compose up -d`
Una vegada fet ya podrem entrar per el nostre navegador al wordpress i procedirem en la instalacio.

---

# 2. Crear usuaris

<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/beaff0b4-4a9d-446b-9db2-d9e81e2cfd17" />

Una vegada dins crearem un usuari editor que es el que farem servir proximament per al plugging de JWT.

---

# 3. Instalar  Plugging JWT

Instalem el plugging de JWT i el activem
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/90aa5b21-b942-472f-886d-79cb3bc2194f" />

Ara dins del plugging, entrarem en l'usuari editor que hem creat per a generar la JWT_AUTH_SECRET_KEY. (A la captura no surt perque ya ho havia fet anteriorment amb este usuari)
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/aaf428bc-68a8-4df7-b1b0-84e658f74ce3" />

Entrarem dins del contenedor amb la comanda `sudo docker exec -it my-wordpress_wordpress_1 bash`
I modificarem el archiu `wp-config.php`
I com podeu vore a la imatge afegirem les linies de configuracio per a definir la JWT_AUTH_SECRET_KET, per a que el plugging puga validar les nostres peticions
<img width="804" height="611" alt="image" src="https://github.com/user-attachments/assets/ecd51638-81ee-49b2-8898-dab2ad84d91c" />

---

# 4. Archiu Get-post.html

Crearem este HTML, que el que fara es parlar amb la API de Wordpress per a crear o actualitzar les pagines.
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/fc6ca206-2bb4-4091-a498-af7b86602afc" />

---

# 5. Archiu Login-And-Post.html

Este archiu s'encarregara de llegir els archius que volem muntar al Wordpress i prepararlos per a que siguen muntats
<img width="800" height="600" alt="image" src="https://github.com/user-attachments/assets/525248ce-a18b-4c6c-9637-3ff2bbe93866" />

---

# 6. Fer servir els HTML

Per a fer servir els htmls anteriors farem servir la comanda `python -m http.server 5500`

Aqui es on muntarem els nostres fitxers
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/32bc943c-d5ca-43a7-b15e-6054d1ca15d0" />

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/aa0191c3-c823-474e-86cb-e6c033297c79" />

---

# 7. Web Final

Aqui podrem vore totes les pagines que hem muntat a la web
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/3ae9e8d7-1d46-47c8-96b4-391f25c0d734" />

I aixi quedaria la nostra web una vegada hem muntat totes les pagines
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/4d4ec884-236d-4946-adc9-8c7be6a4fd5b" />









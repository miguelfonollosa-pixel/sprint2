# 1. Prerequisits i esquema

* Servidor (Linux) amb **Docker** i **Docker Compose**
* IP del servidor a la LAN: `172.20.10.3`
* WordPress accessible a: `http://172.20.10.3:80`
* PC client a la mateixa xarxa amb navegador

---

# 2. Docker Compose: WordPress + MariaDB

Este es la configuracio del wordpress i mariadb, aqui el que posem el que configurem es els usuaris que tindran mariadb i wordpress, i tmb molt important per quins ports podrem entrar al wordpress.

<img width="677" height="786" alt="image" src="https://github.com/user-attachments/assets/38dc0588-c5b9-4ddc-83d2-c2a5de86e249" />

Despres de configurar el contenedor los tindrem que arrancar amb la comanda `docker compose up -d`
Una vegada fet ya podrem entrar per el nostre navegador al wordpress i procedirem en la instalacio.

---

# 3. Crear usuaris

<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/beaff0b4-4a9d-446b-9db2-d9e81e2cfd17" />

Una vegada dins crearem un usuari editor que es el que farem servir proximament per al plugging de JWT.

---

# Instalar  Plugging JWT

Instalem el plugging de JWT i el activem
<img width="1893" height="937" alt="image" src="https://github.com/user-attachments/assets/90aa5b21-b942-472f-886d-79cb3bc2194f" />

Ara dins del plugging, entrarem en l'usuari editor que hem creat i generarem un token
<img width="1911" height="982" alt="image" src="https://github.com/user-attachments/assets/aaf428bc-68a8-4df7-b1b0-84e658f74ce3" />

Entrarem dins del contenedor amb la comanda `sudo docker exec -it my-wordpress_wordpress_1 bash`
I modificarem el archiu `wp-config.php`
I com podeu vore a la imatge posarme les dos linees que he posat i a la de dalt afegirem el token
<img width="804" height="611" alt="image" src="https://github.com/user-attachments/assets/ecd51638-81ee-49b2-8898-dab2ad84d91c" />

# Archiu Get-post.html

Crearem este HTML, que el que fara es verificar la conexio amb la API de Wordpress i posteriorment crear o actualitzar el contingut de Wordpress
<img width="981" height="745" alt="image" src="https://github.com/user-attachments/assets/fc6ca206-2bb4-4091-a498-af7b86602afc" />

# Archiu Login-And-Post.html

Este archiu s'encarregara de llegir els archius que volem muntar al Wordpress i prepararlos per a que siguen muntats
<img width="1030" height="742" alt="image" src="https://github.com/user-attachments/assets/525248ce-a18b-4c6c-9637-3ff2bbe93866" />

# Fer servir els HTML

Per a fer servir els htmls anteriors farem servir la comanda `python -m http.server 5500`

Aqui es on muntarem els nostres fitxers
<img width="1445" height="896" alt="image" src="https://github.com/user-attachments/assets/32bc943c-d5ca-43a7-b15e-6054d1ca15d0" />

<img width="1918" height="863" alt="image" src="https://github.com/user-attachments/assets/aa0191c3-c823-474e-86cb-e6c033297c79" />

# Web Final

Aqui podrem vore totes les pagines que hem muntat a la web
<img width="1893" height="902" alt="image" src="https://github.com/user-attachments/assets/3ae9e8d7-1d46-47c8-96b4-391f25c0d734" />

I aixi quedaria la nostra web una vegada hem muntat totes les pagines
<img width="1918" height="851" alt="image" src="https://github.com/user-attachments/assets/4d4ec884-236d-4946-adc9-8c7be6a4fd5b" />









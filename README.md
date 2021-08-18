Paso 1 - Estando en la VM (máquina virtual) activa, lo primero que hay que hacer es instalar Git en la VM
# sudo yum install git

Paso 2 - Posteriormente, hay que instalar Docker en la VM, y lo primero es instalar las utilidades de yum
# sudo yum install -y yum-utils

Paso 3 - Teniendo instaladas las utilidades de yum, ahora podemos instalar docker, pero hay que establecer un repositorio que sea estable
# sudo yum-config-manager \
#    --add-repo \
#    https://download.docker.com/linux/centos/docker-ce.repo

Paso 4 - Una vez especificado el repositorio estable ahora podemos instalar docker
# sudo yum install docker-ce docker-ce-cli containerd.io
Nota: Hay que seleccionar la opción Y(S) en las dos preguntas que hace en esta instalación

Paso 5 - Ya que tenemos instalado docker, ahora tenemos que iniciar docker
# sudo systemctl start docker

Paso 6 - Para probar que docker está funcionando, se puede ejecutar la siguiente instrucción
# sudo docker ps

Paso 7 - Estando en la VM (máquina virtual) y una vez instalado git y docker, hay que clonar este git con el siguiente comando:
# git clone https://github.com/jeaggo/streamlit_app.git

Paso 8 - Cuando se clona el git, lo siguiente es construir (cargar) el contenedor (docker) en la VM y se realiza con el siguiente comando:
# sudo docker build -t streamlitapp:latest .

Paso 9 - Posteriormente hay que inicializar el contenedor para que este acitivo y esto se realiza con el siguiente comando.
# sudo docker run --name streamlit-container -p 8501:8501 -d streamlitapp:latest 

Paso 10 - En la sección denominada "Activate Cloud Shell" de la VM en GCP hay que activar el puerto 8501 para que tenga salida, por lo que hay que ejecutar el siguiente comando:
# gcloud compute firewall-rules create streamlit --allow tcp:8501

Ejemplo de aplicación web con streamlit usando una VM (máquina virtual) en Google Cloud Platform (GCP)

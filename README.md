Estando en la VM (máquina virtual) y una vez instalado git y docker, hay que clonar este git con el siguiente comando:
# git clone https://github.com/jeaggo/streamlit_app.git

Cuando se clona el git, lo siguiente es construir (cargar) el contenedor (docker) en la VM y se realiza con el siguiente comando:
# sudo docker build -t streamlitapp:latest .

Posteriormente hay que inicializar el contenedor para que este acitivo y esto se realiza con el siguiente comando.
# sudo docker run --name streamlit-container -p 8501:8501 -d streamlitapp:latest 

En la sección denominada "Activate Cloud Shell" de la VM en GCP hay que activar el puerto 8501 para que tenga salida, por lo que hay que ejecutar el siguiente comando:
# gcloud compute firewall-rules create streamlit --allow tcp:8501

Ejemplo de aplicación web con streamlit usando una VM (máquina virtual) en Google Cloud Platform (GCP)

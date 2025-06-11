# latamsourcing
# 1. Clona el repositorio recién creado
git clone git@github.com:TU_USUARIO/latam-github-sourcing.git
cd latam-github-sourcing

# 2. Crea un entorno y un requirements.txt
python3 -m venv venv
source venv/bin/activate
pip install requests
pip freeze > requirements.txt

# 3. Crea la carpeta de scripts y añade tu código
mkdir src
# Abre tu editor y guarda el script como src/sourcing_latam.py

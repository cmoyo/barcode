## Barcode Service

Barcode Service is a Django web application designed to run in a Docker container. A `docker-compose.yml` file is included that builds and runs a full stack including database and reverse-proxy (Nginx).

### Getting up and running

Assuming Docker and `docker-compose` are installed, the commands to get the application up and running include:

    docker-compose build

    docker-compose up

    docker-compose exec web python manage.py migrate

To quit the application, press <kbd>Ctrl</kbd>+<kbd>C</kbd>.
### About the bar code generation endpoint

Barcode Generation Service currently supports:
- EAN8 barcode generation => by default
- Height & Width => Float, calculated as  mm
- Background and Foreground colours => Hex value, minus the #
- Initially picked Poemtree package to ouput EAN8 barcode, as most closely resembles barcode image provided
- Used python-barcode package for SVG output
- Business Decision required on which Barcode style to go for

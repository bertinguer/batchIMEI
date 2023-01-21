# batchIMEIchecker

Script para calcular dígitos de control de IMEI
Este script permite calcular el dígito de control de un número IMEI y verificar si un número IMEI es válido. Además, también permite procesar un archivo CSV de entrada y escribir los resultados en un archivo CSV de salida.

La primera línea del input no se procesa

## Requisitos

pip install -r requirements.txt

## Uso

python batchimeicheck.py input.csv output.csv

## Funciones

calculate_check_digit(imei): toma un número IMEI como argumento y devuelve el dígito de control calculado.

is_valid_imei(imei): toma un número IMEI como argumento y devuelve el número IMEI válido con el dígito de control calculado.

process_csv(input_file, output_file): toma dos argumentos, el nombre del archivo CSV de entrada y el nombre del archivo CSV de salida. Lee el archivo de entrada, procesa cada número IMEI y escribe los resultados en el archivo de salida.

## Licencia
Este proyecto se encuentra bajo la licencia MIT.

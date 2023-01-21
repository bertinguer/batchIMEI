import csv
import sys

def calculate_check_digit(imei):
    imei = str(imei)
    check_digit = 0
    for i, c in enumerate(imei):
        if i % 2 != 0:
            d = int(c) * 2
            if d > 9:
                d -= 9
            check_digit += d
        else:
            check_digit += int(c)
    check_digit = (10 - (check_digit % 10)) % 10
    return check_digit

def is_valid_imei(imei):
    imei = str(imei)[:14]
    check_digit = calculate_check_digit(imei)
    imei = imei + str(check_digit)
    return imei

def process_csv(input_file, output_file):
    with open(input_file, 'r') as f_in, open(output_file, 'w', newline='') as f_out:
        reader = csv.reader(f_in)
        writer = csv.writer(f_out)
        headers = next(reader)
        headers.append('IMEI CALCULADO')
        writer.writerow(headers)
        for row in reader:
            imei = row[0]
            imei_valid = is_valid_imei(imei)
            row.append(imei_valid)
            writer.writerow(row)

if len(sys.argv) != 3:
    print("Uso: python nombre_script.py input.csv output.csv")
    sys.exit(1)

input_file = sys.argv[1]
output_file = sys.argv[2]
process_csv(input_file, output_file)

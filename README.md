# Функция для копирования строки из одного файла в другой
def copy_line(source_file, destination_file, line_number):
    try:
        with open(source_file, 'r') as source, open(destination_file, 'a') as destination:
            lines = source.readlines()
            if 1 <= line_number <= len(lines):
                line_to_copy = lines[line_number - 1]
                destination.write(line_to_copy)
                print(f"Строка {line_number} скопирована из {source_file} в {destination_file}.")
            else:
                print("Неверный номер строки.")
    except FileNotFoundError:
        print("Файл не найден.")

# Имя файлов
source_file_name = 'source.txt'
destination_file_name = 'destination.txt'

# Получаем номер строки от пользователя
line_number = int(input("Введите номер строки для копирования: "))

# Вызываем функцию копирования
copy_line(source_file_name, destination_file_name, line_number)

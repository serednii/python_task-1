# python_task-1
## Завдання 1: (5 балів)
Реалізувати програму-імітатор простого менеджера пам’яті. Користувач вводить кількість комірок пам’яті та максимальну кількість комірок для виводу в одному рядку консолі з клавіатури. Після цього робота програми стає циклічною. Для виконання користувач може вводити 5 команд: allocate <num_cells> – виділити блок пам’яті розміром <num_cells> комірок (команда виводить в консоль номер першої комірки виділеного блоку – <block_id>), free <block_id> – звільнити блок, print – вивести структуру блоків пам’яті у консоль, exit – завершити роботу програми, help – вивести коротку інформацію про команди. Намагатись оптимізувати продуктивність алгоритму виділення блоків.
Приклад роботи з програмою:
Please set memory size and max output width:
>30 10
Type 'help' for additional info.
>help
Available commands:

 help  - show this help
 exit  - exit this program
 print - print memory blocks map
 allocate <num> - allocate <num> cells. Returns block first cell number
 free <num> - free block with first cell number <num>

# >print
# |                   |
# |                   |
# |                   |
# >allocate 5
# 0
# >print
# |0xxxxxxxx|         |
# |                   |
# |                   |
# >allocate 3
# 5
>print
|0xxxxxxxx|5xxxx|   |
|                   |
|                   |
>allocate 4
8
>allocate 10
12
>print
|0xxxxxxxx|5xxxx|8xx|
|xxx|12xxxxxxxxxxxxx|
|xxx|               |
>free 5
>print
|0xxxxxxxx|     |8xx|
|xxx|12xxxxxxxxxxxxx|
|xxx|               |
>free 8
>print
|0xxxxxxxx|         |
|   |12xxxxxxxxxxxxx|
|xxx|               |
>allocate 6
5
>print
|0xxxxxxxx|5xxxxxxxx|
|x| |12xxxxxxxxxxxxx|
|xxx|               |
>allocate 3
22
>print
|0xxxxxxxx|5xxxxxxxx|
|x| |12xxxxxxxxxxxxx|
|xxx|22xxx|         |
>exit

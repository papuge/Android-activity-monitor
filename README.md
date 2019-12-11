# Android-Task-Manager

*Курсовой проект по предмету "Архитектура вычислительных систем"*  

## Цели работы  
Создать мобильное приложение, в рамках которого:
* Научиться получать статистику по расходу памяти и процессора  
* Отображать общую занятость памяти и процессора
* Графически представлять процетное соотношение потребления ресурсов работающими процессами

## Что должно получиться  
Мобильное приложение, графически представляющее загруженность системы разными процессами с использованием NDK.**  
** - необходимую информацию о процессах в Linux можно получать из псевдо-файловой системы */proc*, для этого не нужен NDK

## Что получилось
Получилось приложение, больше похожее на *activity monitor*, в котором есть
* Динамическое отображение загруженности процессора в виде графика и значения
* Получение текущих процессов из */proc* (предположительно в рамках одного приложения)
* Вывод у процессов обновляющихся значений по потреблению памяти и мощности процессора из user space и из system space  

### Only for <26 api  
Начиная с 26-ой версии android, чтение из /proc было запрещено, поэтому протестировать приложение можно на более ранних версиях android. 

### Update
Для доступа ко всем процессам и их ресурсам приложение было переделано для устройств с root. Данные получаются после выполнения команды `top -n 1`.  

read: read [-ers] [-a array] [-d delim] [-i text] [-n nchars] [-N nchars] [-p prompt] [-t timeout] [-u fd] [name ...]
Прочтите строку из стандартного ввода и разделите ее на поля.

Читает одну строку из стандартного ввода или из файлового дескриптора FD если задана опция -u .
Строка разбивается на поля, как и при разделении слов, и первое слово назначается первому ИМЕНИ, 
второе слово - второму ИМЕНИ и так далее, а любые оставшиеся слова назначаются последнему ИМЕНИ. 
Только символы, найденные в  $IFS , распознаются как разделители слов.

Если ИМЕНИ не указаны, прочитанная строка сохраняется в переменной REPLY.

Параметры:
  -a array    - присвоить прочитанные слова последовательным индексам переменной массива ARRAY, начиная с нуля
  -d delim    - продолжать, пока не будет прочитан первый символ DELIM, а не новая строка
  -e          - использовать Readline для получения строки
  -i text     - использовать ТЕКСТ в качестве начального текста для строки чтения
  -n nchars   - возвращаются после чтения символов NCHARS вместо ожидания новой строки, но соблюдают разделитель, если перед разделителем читается меньше, чем NCHARS символов
  -N nchars   - возвращаются только после чтения точно NCHARS символов, если не встречается EOF или время чтения не истекло, игнорируя любой разделитель
  -p prompt   - выводит строку PROMPT без завершающей новой строки перед попыткой чтения
  -r          - не позволять обратной косой черте экранировать любые символы
  -s          - не отображать ввод, поступающий с терминала
  -t timeout  - тайм-аут и возврат ошибки, если полная строка ввода не была прочитана в течение TIMEOUT секунд. Значение переменной TMOUT - тайм-аут по умолчанию. TIMEOUT  может быть дробным числом. Если TIMEOUT равен 0, чтение возвращается немедленно, без попытки чтения каких-либо данных, возвращая успех только в том случае, если входные данные доступны в указанном дескрипторе файла. Статус выхода больше 128, если превышен тайм-аут.
  -u fd       - читать из файлового дескриптора FD вместо стандартного ввода.
Статус выхода:
  Код возврата равен нулю, если не обнаружен конец файла, время чтения не истекло (в этом случае оно больше 128), возникает ошибка присвоения переменной или недопустимый дескриптор файла указан в качестве аргумента для -u.
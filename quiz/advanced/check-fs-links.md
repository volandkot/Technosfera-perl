Написать скрипт для обхода файловой системы. Скрипт должен проверять, что имеющиеся жесткие и символические ссылки не образуют колец и не позволяют выйти за пределы заданного каталога.

Пример вызова скрипта:

`check-fs-links --ignore-symlinks /path/to/check`

Ключ --ignore-symlinks отключает проверку символических ссылок, при его наличии они должны восприниматься как обычные файлы.

Пример кольца, сделанного при помощи символической ссылки:

```
/tmp/a
/tmp/a/1
/tmp/a/2
/tmp/a/2/1 -> /tmp/a
```

Пример символической ссылки, позволяющей покинуть заданный каталог:

```
/tmp/a
/tmp/a/1 -> /bin/bash
```
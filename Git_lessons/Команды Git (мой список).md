- **`git branch [имя-ветки]`**
  Позволяет создать новую ветку.

- **`git checkout [имя-ветки]`**
  Переключается на указанную ветку и обновляет рабочую директорию

- **`git checkout -b [your branch name]`**
  Позволяет создать новую ветку и переключиться на неё с помощью одной команды:






### Git Rebase

Второй способ объединения изменений в ветках - это **rebasing**.(первый - **merge**) При ребейзе Git по сути копирует набор коммитов и переносит их в другое место.

Несмотря на то, что это звучит достаточно непонятно, преимущество **rebase** в том, что c его помощью можно делать чистые и красивые линейные последовательности коммитов. История коммитов будет чище, если вы применяете **rebase**.



ДО:

<img src="https://github.com/user-attachments/assets/ba974c01-2706-4111-8330-2a18e7cbb6b3" width="80%" />

ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/7f849d16-70c2-4d7f-9649-f046631609c6" width="50%" />



<img src="https://github.com/user-attachments/assets/3c1361fe-2cbb-4502-ad63-8c0bdf850641" width="50%" />

<img src="https://github.com/user-attachments/assets/a65fd0d2-ed34-4a8d-8804-98bb1d6731b5" width="50%" />



### HEAD
















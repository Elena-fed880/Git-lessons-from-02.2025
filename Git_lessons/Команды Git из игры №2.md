## Удалённые репозитории в Git
На самом деле удалённые репозитории в Git не так сложны, как кажутся на первый взгляд. Кажется, что в современном мире облачных вычислений под термином «удалённый репозиторий» подразумевается что-то сложное и загадочное. Однако, удалённые репозитории — это всего-навсего копии вашего репозитория, хранящиеся на другом компьютере. Обычно вы можете связываться с этим другим компьютером через Интернет, что позволяет вам передавать коммиты туда и сюда.

Как уже было сказано, удалённые репозитории обладают рядом замечательных свойств:

- В первую очередь, удалённые репозитории - это замечательное средство резервного копирования! Насколько вам известно, локальные репозитории способны восстанавливать файлы, используя предыдущие состояния, но вся эта информация хранится локально. Потеряв все свои локальные данные, вы способны восстановить их при наличии копии своего репозитория на другом компьютере.

- Что ещё более важно, удалённые репозитории позволяют сделать процесс разработки более социальным! Теперь, когда копия вашего проекта размещена в другом месте, ваши друзья запросто могут внести свой вклад в ваш проект или забрать последние и актуальные изменения.

Набирает популярность использование web-сайтов для визуализации активности удалённых репозиториев (например, GitHub).

## Наша команда для создания удалённого репозитория
До настоящего момента мы были сфокусированы на изучении основ работы с локальным репозиторием (ветвление, слияние, перемещение и т.д.). Однако теперь, когда мы хотим научиться работать с удалёнными репозиториями, нам нужны новые команды для настройки рабочей среды для этих упражнений. Такой командой нам послужит **`git clone`**

Технически, **`git clone`** в реальной жизни - это команда, которая создаст локальную копию удалённого репозитория (например, с GitHub). На наших занятиях в Learn Git Branching мы используем эту команду немного иначе - **`git clone`** создаёт удалённый репозиторий на основе вашего локального репозитория. На самом деле, это является полной противоположностью реальной команды, однако такой подход поможет нам наладить связь между склонированным и удалённым репозиторием. Давайте просто запустим эту команду.

<img src="https://github.com/user-attachments/assets/b14f27e2-7596-46dd-abbe-b165b47aa82b" width="70%" />


## Удалённые ветки в Git
Теперь, когда вы уже увидели **`git clone`** в действии, давайте углубимся в детали и посмотрим что же на самом деле изменилось.

Во-первых, вы должны были заметить, что у нас в локальном репозитории появилась новая ветка с именем **`o/main`**. Такой тип ветки называется **удалённой веткой**. Поскольку удалённые ветки играют важную и уникальную роль, они обладают рядом специальных свойств.

Удалённые ветки отражают **состояние** удалённых репозиториев (с того момента, как вы обращались к этим удалённым репозиториям в последний раз). Они позволяют вам отслеживать и видеть разницу между вашими локальными наработками и тем, что было сделано другими участниками - важный шаг, который необходимо делать, прежде чем делиться своими наработками с другими.

Важным свойством удалённых веток является тот факт, что когда вы извлекаете их, вы отделяете `(detaching) HEAD`. Git делает это потому, что вы не можете работать непосредственно в этих ветках; сперва вам необходимо сделать наработки где-либо, а уж затем делиться ими с удалёнными репозиториями (после чего ваши удалённые ветки будут обновлены).


## Что такое `o/` в названии ветки?
Вы, наверное, догадались, что первый символ **`o/`** в названии ветки служит для обозначения именно удалённых веток. Да. Удалённые ветки также имеют (обязательное) правило именования - они отображаются в формате:

- **`<удалённый репозиторий>/<имя ветки>`**

Следовательно, если вы взглянете на имя ветки **o/main**, то здесь main - это имя ветки, а o - это имя удалённого репозитория.

Большинство разработчиков именуют свои главные удалённые репозитории не как `o`, а как `origin`. Также общепринятым является именование удалённого репозитория как **`origin`**, когда вы клонируете репозиторий командой **`git clone`**.

К сожалению, полное имя origin не помещается на элементах дизайна наших уроков, поэтому мы используем краткое `o` :( Просто помните, когда вы пользуетесь git в реальном проекте, ваш удалённый репозиторий скорее всего будет называться `origin`!


- **`git checkout o/main; git commit`**

ДО: 
<img src="https://github.com/user-attachments/assets/685bd6d0-334f-4db8-8bea-607757aa3074" width="70%" />

ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/d10552d5-4a12-4682-af1e-3df2356bb763" width="40%" />

- Как вы можете видеть, git отделил (detached) HEAD и не обновил `o/main`, когда мы добавили новый коммит. Всё потому, что `o/main` обновится тогда и только тогда, когда обновится сам удалённый репозиторий.


ЗАДАЧА:

Для завершения уровня выполните коммит единожды на `main`, а затем на `o/main` (предварительно переключившись на эту ветку). Это наглядно продемонстрирует поведение удалённых веток, а также покажет, как изменения влияют на состояние удалённых репозиториев.

ДО: 
<img src="https://github.com/user-attachments/assets/3ea5a481-2e65-4376-9674-099c80855037" width="30%" />

ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/e5f107d2-9c47-4a7b-a424-31fe27646f91" width="70%" />




## Git Fetch
Работа с удалёнными git репозиториями сводится к передаче данных в и из других репозиториев. 
До тех пор, пока мы можем отправлять коммиты туда-обратно, мы можем делиться любыми изменениями, которые отслеживает git (следовательно, делиться новыми файлами, свежими идеями, любовными письмами и т.д.).

В этом уроке вы научитесь тому, как **извлекать данные из удалённого репозитория** - и для этого у нас есть соответствующая команда **`git fetch`**.

- **`git fetch`** - скачивает недостающие коммиты из удаленного репозитория в локальный.  Удалёенная ветка в локальном репозитории отображает эти изменения соответствующим образом.
  
ДО: 

<img src="https://github.com/user-attachments/assets/70007cc3-7c3e-410a-9bf9-bfe53eedd92f" width="70%" />

ПОСЛЕ: 

<img src="https://github.com/user-attachments/assets/7083e7a1-71d2-4c14-8161-5839a9e542f8" width="70%" />


### Что делает fetch

git fetch выполняет две и только две основные операции. А именно:

- связывается с указанным удалённым репозиторием и забирает все те данные проекта, которых у вас ещё нет, при этом...
- у вас должны появиться ссылки на все ветки из этого удалённого репозитория (например, `o/main`)

Фактически, **git fetch** синхронизирует **локальное** представление удалённых репозиториев с тем, что является **актуальным** на текущий момент времени.

Насколько вы помните, в предыдущем уроке мы сказали, что удалённые ветки отображают состояние удалённых репозиториев на тот момент когда вы 'общались' с ними в последний раз. 
git fetch является тем механизмом, который даёт вам возможность общаться с удалёнными репозиториями! Надеюсь, что связь между удалёнными ветками и командой git fetch теперь прояснилась.

git fetch обычно 'общается' с удалёнными репозиториями посредством Интернета (через такие протоколы, как **http://** или **git://**).



### Чего fetch не делает

Важно отметить, что команда `git fetch` забирает данные в ваш локальный репозиторий, но не сливает их с какими-либо вашими наработками и не модифицирует то, над чем вы работаете в данный момент.
Важно это помнить и понимать, потому что многие разработчики думают, что, запустив команду `git fetch`, они приведут всю свою локальную работу к такому же виду, как и на удалённом репозитории. Команда всего лишь скачивает все необходимые данные, но вам потребуется вручную слить эти данные с вашими, когда вы будете готовы. В следующих уроках мы научимся это делать :D

Одним словом, вы можете относиться к `git fetch` как  к **процедуре скачивания недостающих файлов с удаленного репозитория**.

ЗАДАЧА:

<img src="https://github.com/user-attachments/assets/968b1b36-65d5-42fe-9f8b-ea3a06ec4ab4" width="70%" />

ЦЕЛЬ:

<img src="https://github.com/user-attachments/assets/90c70ccf-1b4f-4fcc-a804-5bd8b11e3177" width="50%" />

РЕШЕНИЕ:

<img src="https://github.com/user-attachments/assets/f921ba37-08cc-4f32-8133-f21da75f4fb4" width="40%" />




## Git Pull

Теперь, когда мы познакомились с тем, как извлекать данные из удалённого репозитория с помощью `git fetch`, давайте обновим нашу работу, чтобы отобразить все эти изменения!

Существует множество вариантов решений - как только у вас имеется локальный коммит, вы можете соединить его с другой веткой. Это значит, вы можете выполнить одну из команд:

- **`git cherry-pick o/main`**
- **`git rebase o/main`**
- **`git merge o/main`**
- и т.д.

Процедура скачивания (fetching) изменений с удалённой ветки и объединения (merging) настолько частая и распространённая, что git предоставляет вместо двух команд - одну! Эта команда - **`git pull`**.


Давайте рассмотрим, как fetch и merge выполняются последовательно:

- **`git fetch; git merge o/main`**

ДО:

<img src="https://github.com/user-attachments/assets/06d232e5-a2ed-4b9d-8ec8-d4180460f76c" width="70%" />

ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/3d1e09eb-ceb0-458f-93b0-57d9e82d2c54" width="70%" />

Опа - мы скачали `C3` с помощью команды `fetch` и затем объединяем эти наработки с помощью `git merge o/main`. 
Теперь наша ветка `main` отображает изменения с удалённого репозитория (в данном случае — с репозитория `origin`)


Что же произойдёт, если вместо этих команд мы воспользуемся `git pull`?

ДО:

<img src="https://github.com/user-attachments/assets/14a42e63-3f55-496c-b4a6-50054324a782" width="70%" />

ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/c816a785-c9a7-4541-9460-251bc1e0189b" width="70%" />


Абсолютно то же самое! Нужно чётко понимать, что `git pull` существенно уменьшает вашу рутинную работу, 
если бы вы использовали `git fetch` и последующее слияние (merging) скаченной ветки.


## Симуляция совместной работы
В данном уроке мы находимся в немного затруднительном положении - для выполнения ряда упражнений нам нужно обучить вас скачивать 
наработки и изменения, которые были сделаны в удалённом репозитории.

Это означает, что нам следует "сделать вид", как будто мы знаем о том, что наш удалённый репозиторий, 
с которым мы работаем, был изменён одним из ваших коллег / друзей / единомышленников. 
Это может быть какая-то ветка, либо же какой-то конкретный коммит.

Для того, чтобы добиться своих целей, нам предоставляется команда со звучным именем **`git fakeTeamwork`**!

Поведение команды **`fakeTeamwork`** по умолчанию заключается в том, чтобы просто "инициировать" коммит на main-е



ДО:

<img src="https://github.com/user-attachments/assets/fba6af76-6ddd-49f3-96e0-14399d4f1964" width="70%" />

- **`git fakeTeamwork`**

  
ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/b9858f01-d72c-46c9-9567-1ab46cf986fd" width="70%" />

Ну вот - удалённый репозиторий был изменён при помощи добавления нового коммита, 
и мы ещё не скачали этот коммит, потому что не запустили команду **`git fetch`**.

____________________________________
ДО:

<img src="https://github.com/user-attachments/assets/3ffb025a-883d-4ece-9053-33af15fbb6ce" width="70%" />

- **`git fakeTeamwork foo 3`**
В данной команде вам доступна возможность указать ветку и количество добавляемых коммитов
  
ПОСЛЕ:

<img src="https://github.com/user-attachments/assets/92dc6ad9-a854-45ee-9938-e14fd9958d9a" width="70%" />

- С помощью одной лишь команды мы симулируем добавление трёх коммитов в ветку **`foo`** на удалённом репозитории.


____________________________________

ЗАДАЧА:

<img src="https://github.com/user-attachments/assets/4ae52da3-d575-49ea-9637-0a80ec1efaa2" width="60%" />

<img src="https://github.com/user-attachments/assets/a18f4da6-4c54-493e-80f4-8aa5a3ec9956" width="40%" />


ЦЕЛЬ:

<img src="https://github.com/user-attachments/assets/daef543c-606a-4bcb-afe6-000b8bd40c42" width="40%" />

РЕШЕНИЕ:

<img src="https://github.com/user-attachments/assets/cd85154e-4257-4aec-89c8-68d932ef11b7" width="40%" />

____________________________________


## Git Push
Хорошо, мы скачали изменения с удалённого репозитория и включили их в наши локальные наработки. 
Всё это замечательно, но **как нам поделиться** своими наработками и изменениями с другими участниками проекта?

Способ, которым мы воспользуемся, является противоположным тому способу, которым мы пользовались ранее для скачивания наработок (**`git pull`**). Этот способ - использование команды **`git push`**!

Команда **`git push`** отвечает за загрузку ваших изменений в указанный удалённый репозиторий, а также включение ваших коммитов в состав удалённого репозитория. По окончании работы команды git push все ваши друзья смогут скачать себе все сделанные вами наработки.

Вы можете рассматривать команду **`git push`** как "публикацию" своей работы. Эта команда скрывает в себе множество тонкостей и нюансов, с которыми мы познакомимся в ближайшее время, а пока что давайте начнём с малого...

замечание - поведение команды **`git push`** без аргументов варьируется в зависимости от значения **`push.default`**, указанной в настройках git-а. Значение по умолчанию зависит от версии git, которую вы используете, однако в наших уроках мы будем использовать значение **`upstream`**. Лучше всегда проверять эту опцию прежде чем push-ить ваши настоящие проекты.


ЗАДАЧА:

<img src="https://github.com/user-attachments/assets/b5d4ac20-8efd-4219-9249-11acb87c02f6" width="40%" />

- Здесь у нас имеются изменения, которых нет в удалённом репозитории. Давайте же закачаем их туда!

РЕШЕНИЕ: 

- **`git push`**

<img src="https://github.com/user-attachments/assets/8b2d35da-1402-401a-a790-a4cc82f3db38" width="40%" />

Вот так - удалённый репозиторий получил новый коммит `C2`, ветка `main` на удалённом репозитории теперь указывает на `C2`,
и наше собственное локальное отображение удалённого репозитория (`o/main`) изменилось соответственно. Всё синхронизировалось!



## Когда наработки расходятся
Вот мы и познакомились с тем, как забирать (pull) чужие коммиты и как закачивать (push) свои наработки и изменения. 
Выглядит всё довольно просто, и не ясно какие же могут возникать у людей трудности со всем этим?

Сложности возникают тогда, когда история репозитория расходится. Прежде чем идти дальше, давайте посмотрим на пример...

















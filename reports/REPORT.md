## Лабораторная работа №3. Отчет.

## Задание на лабораторную работу:

1. Создать публичный репозиторий с названием lab03 и с лиценцией MIT 
2. Ознакомиться со ссылками учебного материала 
3. Выполнить инструкцию учебного материала 
4. Составить отчет и отправить ссылку личным сообщением в Slack 

## Выполнение работы.
	
В соответствии с последовательностью, определенной заданием на лабораторную работу, были выполнены следующие действия:
1. Проведено ознакомление по приведенным ссылкам со следующими материалами по GitHub, Bitbucket, Gitlab, LearnGitBranching.
2. Для успешного выполнения аздания создан новый пустой репозиторий lab03 с лицензией MIT, попутно создан файл .gitignore 
3. Выполнена следующая последовательность команд:


## Tutorial
```ShellSession
$ export GITHUB_USERNAME=vaulex
$ export GITHUB_EMAIL=krasauchek-s-iy@ya.ru
$ alias edit=subl
$ cd ${GITHUB_USERNAME}/workspace
$ source scripts/activate
$ mkdir projects/lab03 && cd projects/lab03
$ git init
$ git config --global user.name ${GITHUB_USERNAME}
$ git config --global user.email ${GITHUB_EMAIL}
$ git config -e --global
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab03.git
$ git pull origin master
$ touch README.md
$ git status
$ git add README.md
$ git commit -m"added README.md"
$ git push origin master

$ git pull origin master
$ git log
$ mkdir sources
$ mkdir include
$ mkdir examples
$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out) {
  out << text;
}

void print(const std::string& text, std::ofstream& out) {
  out << text;
}
EOF
$ cat > include/print.hpp <<EOF
#include <string>
#include <fstream>
#include <iostream>

void print(const std::string& text, std::ostream& out = std::cout);
void print(const std::string& text, std::ofstream& out);
EOF
$ cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv) {
  print("hello");
}
EOF
$ cat > examples/example2.cpp <<EOF
#include <fstream>
#include <print.hpp>

int main(int argc, char** argv) {
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
$ edit README.md
$ git status
$ git add .
$ git commit -m"added sources"
$ git push origin master
```
Результат выполнения команды git log:
```ShellSession
commit b946fd89b43ead40423c0bac3e40270b72f8a987
Author: vaulex <krasauchek-s-iy@ya.ru>
Date:   Wed Dec 13 18:14:51 2017 +0300

    добавлен .gitignore

commit 924b2fa7e8ffda3df2f95347e5fcad7d67c04f0a
Author: vaulex <krasauchek-s-iy@ya.ru>
Date:   Wed Dec 13 18:08:40 2017 +0300

    added README.md

commit d0ff50b101152969e3ab8fb7dacc833525b45fab
Author: vaulex <34100081+vaulex@users.noreply.github.com>
Date:   Wed Dec 13 18:03:13 2017 +0300

    Initial commit
```
## Report
```ShellSession
$ cd ~/workspace/labs/
$ export LAB_NUMBER=03
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER}.git tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gistup -m "lab${LAB_NUMBER}"
```

## В результате выполнения блока Tutorial:

осуществлено наполнение репозитория lab03 файлами, содержащими исходные коды с сохранение структуры каталогов проекта определены конфигурационные;
осуществлено редактирование файла readme.md и коммит изменения в репозиторий.
	
## В результате выполнения блока Report:

с git-репозитория https://github.com/tp-labs/lab03 сделана копия задания в локальный проект в папку tasks/lab03
файл readme скопированный из локальной копии репозитория tp-lab перемещен в папку report локального проекта;
файла readme отредактирован после чего файл выгружен в git-репозиторий.
	 
Составлен отчет о работе.

	
## Выводы:
В ходе проделанной работы проведена ознакомительная работа с работой git-репозитория, команд push/pull/commit  и связанный программ терминального окна Unix-среды.

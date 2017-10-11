## Laboratory work III

Данная лабораторная работа посвещена изучению систем контроля версий на примере **Git**.

```bash
$ open https://git-scm.com
```

## Tasks

- [x]. Создать публичный репозиторий с названием **lab03** и с лиценцией **MIT**
- [x] 2. Ознакомиться со ссылками учебного материала
- [x] 3. Выполнить инструкцию учебного материала
- [x] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```ShellSession
$ export GITHUB_USERNAME=NovikovAnton # Установка значения GITHUB_USERNAME
$ export GITHUB_EMAIL=jNova916@bk.ru # Установка значения GITHUB_EMAIL
$ alias edit=vim # Настройка текстового редактора
```

```ShellSession
$ mkdir lab03 && cd lab03 # Создание папки lab03 и переходим туда
$ git init # Процесс инициализации
$ git config --global user.name ${GITHUB_USERNAME} # Прописка GITHUB_USERNAME в файл .gitconfig
$ git config --global user.email ${GITHUB_EMAIL} # Прописка GITHUB_EMAIL в файл .gitconfig
$ git config -e --global # Проверка файла через текстовый редактор nano
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab03 # Добавление удаленного репозитория
$ git pull origin master # Извлечение и заполнение данного рпозитория
$ touch README.md # Создание файла
$ git status # Состояние проекта
$ git add README.md # Добавление файла в коммит
$ git commit -m"added README.md" # коммит файла
$ git push origin master # Загрузка в репозиторий
```

Добавить на сервисе **GitHub** в репозитории **lab03** файл **.gitignore**
со следующем содержимом:

```ShellSession
*build*/
*install*/
*.swp
```

```ShellSession
$ git pull origin master
$ git log # Лог процесса гита
```

```ShellSession
$ mkdir sources # Создание папки sources
$ mkdir include # Создание папки include
$ mkdir examples # Создание папки examples
$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out) {
  out << text;
}

void print(const std::string& text, std::ofstream& out) {
  out << text;
}
EOF
```

```ShellSession
$ cat > include/print.hpp <<EOF
#include <string>
#include <fstream>
#include <iostream>

void print(const std::string& text, std::ostream& out = std::cout);
void print(const std::string& text, std::ofstream& out);
EOF
```

```ShellSession
$ cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv) {
  print("hello");
}
EOF
```

```ShellSession
$ cat > examples/example2.cpp <<EOF
#include <fstream>
#include <print.hpp>

int main(int argc, char** argv) {
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
```

```ShellSession
$ edit README.md # Редактор файла
```

```ShellSession
$ git status # Проверка состояния проекта
$ git add . # Добавление всех существующих файлов
$ git commit -m"added sources" # Коммит всех файлов
$ git push origin master # Загрузка в репозиторий
```

## Report

```ShellSession
$ cd ~/workspace/labs/ # Переход в папку labs
$ export LAB_NUMBER=03 # Установка значения LAB_NUMBER
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER} #Загрузка гита с github.com
$ mkdir reports/lab${LAB_NUMBER} # Переход в lab03
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md # Копирование файла в папку
$ cd reports/lab${LAB_NUMBER} # Переход в папку lab03
$ edit REPORT.md # Редактор файла
$ gistup -m "lab${LAB_NUMBER}" # Коммит файла
```

## Links

- [GitHub](https://github.com)
- [Bitbucket](https://bitbucket.org)
- [Gitlab](https://about.gitlab.com)
- [LearnGitBranching](http://learngitbranching.js.org/)

```
Copyright (c) 2017 Братья Вершинины
```

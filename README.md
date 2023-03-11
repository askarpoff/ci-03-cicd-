# ci-03-cicd
## Знакомоство с SonarQube

### Основная часть

1. Создайте новый проект, название произвольное.
2. Скачайте пакет sonar-scanner, который вам предлагает скачать SonarQube.
3. Сделайте так, чтобы binary был доступен через вызов в shell (или поменяйте переменную PATH, или любой другой, удобный вам способ).
4. Проверьте `sonar-scanner --version`.
![image](https://user-images.githubusercontent.com/108946489/224488599-e5fc06d2-69b0-4e35-8850-073d9d5495d9.png)

5. Запустите анализатор против кода из директории [example](./example) с дополнительным ключом `-Dsonar.coverage.exclusions=fail.py`.
6. Посмотрите результат в интерфейсе.
![image](https://user-images.githubusercontent.com/108946489/224488625-c6204cdc-166b-4eca-937e-79f561bcd33e.png)
7. Исправьте ошибки, которые он выявил, включая warnings.
8. Запустите анализатор повторно — проверьте, что QG пройдены успешно.
9. Сделайте скриншот успешного прохождения анализа, приложите к решению ДЗ.
![image](https://user-images.githubusercontent.com/108946489/224488656-c8de7f91-9799-4b6f-94e3-defaae2ba2ed.png)

## Знакомство с Nexus

### Основная часть

1. В репозиторий `maven-public` загрузите артефакт с GAV-параметрами:

 *    groupId: netology;
 *    artifactId: java;
 *    version: 8_282;
 *    classifier: distrib;
 *    type: tar.gz.
   
2. В него же загрузите такой же артефакт, но с version: 8_102.
3. Проверьте, что все файлы загрузились успешно.
![image](https://user-images.githubusercontent.com/108946489/224491596-9e5d2d44-7f39-4522-8823-2b5d0e3f9e6a.png)

4. В ответе пришлите файл `maven-metadata.xml` для этого артефекта.
https://github.com/askarpoff/ci-03-cicd-/blob/main/maven-metadata.xml

### Знакомство с Maven

### Основная часть

1. Поменяйте в `pom.xml` блок с зависимостями под ваш артефакт из первого пункта задания для Nexus (java с версией 8_282).
2. Запустите команду `mvn package` в директории с `pom.xml`, ожидайте успешного окончания.
3. Проверьте директорию `~/.m2/repository/`, найдите ваш артефакт.
4. В ответе пришлите исправленный файл `pom.xml`.

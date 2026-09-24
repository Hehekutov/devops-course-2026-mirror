# Практики 2 и 3 — отчёты

Кудояров Денис Рустемович, группа ЭФБО-18-24.

## Материалы
- [Практика 2](practice-2.md)
- [Практика 3](practice-3.md)
- [Контрольные вопросы](control_questions.md)
- [Скриншоты протоколов](screenshots.md)
- [Полный журнал Git](evidence/git-session.txt)
- [Проверки Python](evidence/verification.txt)

## Что осталось с участием студента
1. Парное Code Review: одногруппник должен оставить содержательный отзыв к [PR №1](https://github.com/Hehekutov/Tools_DevOps/pull/1); нужно также проверить его PR. Затем исправить замечание новым коммитом, выполнить Squash and merge и удалить feature/hobby-project. Эти действия пока не выполнены.
2. VS Code открыл Tools_DevOps в ограниченном режиме: Source Control отключён до ручного подтверждения доверия папке. Поэтому просмотр diff и коммит через UI пока не выполнены. GitLens установлен; ide_notes.md создан и закоммичен через CLI.

## Как проверить локально
```powershell
git log --graph --oneline --all -25
git remote -v
git remote get-url --push --all origin
git show feature/calculator:calculator.py
git show hotfix/urgent-fix:calculator.py
git log --oneline practice/rebase-playground -2
git log --oneline prep/kr-practice -1
```

Ветка practice/rebase-playground оставлена только локально по требованию ДЗ №2. Две переписанные истории сохранены в протоколах; выполнялся настоящий interactive rebase с редактором плана и сообщений.

Скриншоты p2/p3 показывают просмотр сохранённого вывода Git в браузере, а не имитируют окно терминала. Рядом есть исходные TXT с хешами, которые можно проверить в репозитории. Скриншоты GitHub и VS Code, если приложены, являются снимками соответствующих приложений.

Для установки hook в новом клоне: `git config core.hooksPath .githooks`.

Результат оформлен в [PR №2](https://github.com/Hehekutov/Tools_DevOps/pull/2).

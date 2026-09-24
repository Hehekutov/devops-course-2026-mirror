# Практическая работа №3

**Кудояров Денис Рустемович, ЭФБО-18-24**

Операции выполнялись настоящими командами Git. В качестве линии интеграции использована codex/practices-2-3 вместо main, чтобы оформить результат отдельным PR и сохранить открытый PR №1. Временные конфликтующие ветки удалены после сохранения их результата. История опубликованных коммитов не переписывалась.

## 1. Merge-конфликт
Две ветки conflict/readme-update-1 и conflict/readme-update-2 изменили одни и те же строки README. Git действительно остановил merge. Результат объединяет информацию о студенте, описание и стек.
- [Конфликт с маркерами](evidence/p3-conflict-before.txt)
- [Разрешённый конфликт и граф](evidence/p3-conflict-after.txt)

## 2. Merge и rebase
Созданы два feature-коммита и независимый коммит в линии интеграции. В demo/merge-result выполнен merge --no-ff; затем исходная feature-ветка перенесена rebase и интегрирована fast-forward.
- [Граф merge](evidence/p3-merge-graph.txt): две линии сходятся в коммите с двумя родителями; исходные коммиты сохраняются.
- [Граф rebase](evidence/p3-rebase-graph.txt): на участке примера коммиты идут последовательно, их хеши изменились. Более старый merge из задания 1 закономерно остаётся ниже в графе.

Деревья файлов двух результатов сравнены и совпадают. В методичке простой merge мог дать fast-forward, а rebase на неизменившуюся базу — ничего не сделать. Отдельный коммит базы обеспечивает настоящее сравнение.

## 3. Interactive rebase
В feature/calculator сделано шесть коммитов из задания. Реальный план git rebase -i HEAD~6: reword, fixup, reword, fixup, reword, drop.
- [Шесть исходных коммитов](evidence/p3-calculator-before.txt)
- [Три чистых коммита и calculator.py](evidence/p3-calculator-after.txt)

Итоговые сообщения: feat: implement add function; feat: implement subtract function; docs: add calculator README. Обе функции и комментарий # fixed сохранены.

## 4. Multi-remote
Использован разрешённый методичкой вариант второго репозитория на GitHub:
- [Основной репозиторий](https://github.com/Hehekutov/Tools_DevOps)
- [Зеркало](https://github.com/Hehekutov/devops-course-2026-mirror)

Remote mirror указывает на зеркало. Для origin заданы оба push-URL явно. SSH GitLab не требуется для выбранного HTTPS/GitHub варианта. Отправлены рабочие ветки, за исключением practice/rebase-playground из ДЗ №2; слепой push --all нарушил бы требование не публиковать эту ветку.

[Настройки и проверка совпадения SHA](evidence/p3-multi-remote.txt).

## 5. Cherry-pick, reflog, revert
- [Cherry-pick](evidence/p3-cherry-pick.txt): перенесён только IMPORTANT_FIX; multiply и divide остались в hotfix/urgent-fix.
- [Reflog](evidence/p3-reflog.txt): temp/lost-branch удалена, коммит найден именно в reflog и восстановлен в temp/recovered-branch. Файл прочитан; временная ветка затем удалена.
- [Revert](evidence/p3-revert.txt): ошибочный коммит сохранён в истории, обратный коммит удаляет BROKEN_CODE.

## Бонус. Hook
[.githooks/commit-msg](../.githooks/commit-msg) проверяет Conventional Commits. Настроен core.hooksPath. Поддержаны обычные автоматические Revert-сообщения, чтобы не мешать заданию 5.

[Отклонённый и успешный коммиты](evidence/p3-hook.txt).

## Домашнее задание
В prep/kr-practice подготовлен [kr_prep.md](../kr_prep.md), три черновых коммита сведены к одному через interactive rebase и отправлены на GitHub.
- [До](evidence/p3-kr-before.txt)
- [После](evidence/p3-kr-after.txt)
- Повторное разрешение конфликта: [до](evidence/p3-kr-conflict-before.txt), [после](evidence/p3-kr-conflict-after.txt).

[Ответы на контрольные вопросы](control_questions.md).


# Работа с git

Создание ветки:

    1. Сначала забирем все изменения из master.
           git pull master
    2. Создадим локальную ветку
           git checkout -b iss42
       Результат:
           Перешел к новой ветке 'iss42'
       При этом создается векта в нашем локальном репо. И наш репо переключается на нее.

    3. Создадим ветку в удаленном репо.
           git push origin iss42
       Результат:
           Total 0 (delta 0), reused 0 (delta 0)
           To git@github.com:suvitorg/coding-style.git
           * [new branch]      iss42 -> iss42
       Теперь в удаленном репо есть наша ветка доступная всем.

    4. Попробуем подтянуть оттуда изменения.
           git pull
        Результат:
           There is no tracking information for the current branch.
           Please specify which branch you want to merge with.
           See git-pull(1) for details

               git pull <remote> <branch>

           If you wish to set tracking information for this branch you can do so with:

               git branch --set-upstream-to=origin/<branch> iss42
        Дело в том что наша локальная и удаленная ветки это по сути ветки разные и надо указать из какой ветки удаленного сервера мы хотим получать изменения в нашу iss42.
        Делаем:
             git branch --set-upstream-to=origin/iss42 iss42
        Результат:
             Branch iss42 set up to track remote branch iss42 from origin.
        Теперь находясь в нашей iss42 мы можем спокойно делать
             git pull.


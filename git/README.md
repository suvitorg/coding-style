
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

Коммиты:
  
    1. Т.к у нас создана ветка в удаленном репо и наша локальная привязана к ней то все стандатно

        git [add/rm] . -all
        git commit -m "comment"

    2. Пуш

        git push origin iss42

    После этого все наши локальны изменения попадают в репо и доступны любому желающему:
        git checkout iss42

Merge:
  
  Т.к мы все изменения вносим тольок в свою ветк то и изменения к нам из репо попадать не будут из других веток. В нашем случае на интересуют текущие изменения из ветки master. Нужно изменения накатаить в нашу ветку.

    1. Переключаемся на ветку мастер.
           git checkout master

       Результат:
           Перешел к ветке 'master'

    2. Забираем текущие изменения
           git pull

    3. Переключаемся обратно нашу ветку
           git checkout iss42
       Результат:
           Перешел к ветке 'iss42'


    4. Делаем merge в нашей ветке с мастером.
        git merge master
        Merge made by the 'recursive' strategy.

    5. Если есть конфликты правим.
        git [add/rm] . -all
        git commit -m "comment"

    6. Заливаем все в нашу ветку.
        git push origin iss42
        Результат:
        Counting objects: 13, done.
        Delta compression using up to 4 threads.
        Compressing objects: 100% (5/5), done.
        Writing objects: 100% (5/5), 598 bytes | 0 bytes/s, done.
        Total 5 (delta 4), reused 0 (delta 0)
        remote: 
        remote: View pull request for iss617 => master:
        remote:   https://bitbucket.org/suvitorg-odoo/format/pull-requests/2?t=1
        remote: 
        To git@bitbucket.org:suvitorg-odoo/format.git
           e860d37..9f1916e  iss617 -> iss617

Пулл реквест:

После того как сделали задачу необходимо создать пулл ревест.
Ссылка для содания есть при пуше, либо надо поти на битбакет и создать пулл реквест на внесение изменений из вашей ветки в мастер.

  1. Создаем пулл реквест. Снимаем галочку удалить ветку после мерджа:
    
        https://bitbucket.org/suvitorg-odoo/format/pull-requests/2?t=1 
  2. После того как ревест одобрен, он попадет в мастер





<h1>Шпаргалка по Git</h1>
<table width="100%" border="1">
    <thead>
        <caption>
            <h3>Создание локального репозитория (ЛР)</h3>
        </caption>
    </thead>
    <tbody>
        <tr>    
            <th width="33%">Действие</th>
            <th width="33%">Комманда</th>
            <th width="33%">Комментарий</th>
        </tr>
        <tr>
            <td>Создание ЛР</td>
            <td><code>git init</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Проверка наличия неотслеживаемых файлов</td>
            <td><code>git status</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Индексация файла (перевод файла в статус отслеживаемого)</td>
            <td><code>git add (название файла с расширением с учетом регистра)</code></td>
            <td>Можно добавить несколько файлов перечислив их через пробел</td>
        </tr>
        <tr>
            <td>Индексация всех файлов (перевод всех файлов в статус отслеживаемых)</td>
            <td><code>git add .</code></td>
            <td>Точка "<code>.</code>" часть команды</td>
        </tr>
        <tr>
            <td>Удаление из индекса</td>
            <td><code>git rm -r --cached .</code></td>
            <td>Удаляет из индекса все папки</td>
        </tr>
        <tr>
            <td>Коммитим файлы в ЛР</td>
            <td><code>git commit -m "(название коммита, например, add README)"</code></td>
            <td>Для первого коммита принято всегда давать название <code>Initial commit</code></td>
        </tr>
    </tbody>
</table>
<table width="100%" border="1">
    <thead>
        <caption>
            <h3>Работа с историей</h3>
        </caption>
    </thead>
    <tbody>
        <tr>    
            <th width="33%">Действие</th>
            <th width="33%">Комманда</th>
            <th width="33%">Комментарий</th>
        </tr>
        <tr>
            <td>Просмотр полной истории</td>
            <td><code>git log</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Просмотр краткой истории</td>
            <td><code>git log --oneline</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Просмотр всей истории при переходе на ранний коммит</td>
            <td><code>git log --oneline --all</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Исправление прошлого коммита в ЛР</td>
            <td><code>git commit --amend -m " (название коммита)"</code></td>
            <td>Отменяет полностью последний коммит в ЛР и создает новый. С помощью данной команды можно так же добавлять новые файлы в этот же коммит</td>
        </tr>
        <tr>
            <td>Отмена изменений в последнем коммите в УР</td>
            <td><code>git revert (хэш коммита)</code></td>
            <td>Хэш коммита - первые 7 цифр</td>
        </tr>
        <tr>
            <td>Вывод одной из прошлых версий</td>
            <td><code>git checkout (хэш коммита)</code></td>
            <td>Хэш коммита - первые 7 цифр</td>
        </tr>
        <tr>
            <td>Возврат к последней актуальной версии коммита</td>
            <td><code>git checkout -</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table width="100%" border="1">
    <thead>
        <caption>
            <h3>Удаленный репозиторий (УР)</h3>
        </caption>
    </thead>
    <tbody>
        <tr>    
            <th width="33%">Действие</th>
            <th width="33%">Комманда</th>
            <th width="33%">Комментарий</th>
        </tr>
        <tr>
            <td>Проверка наличия связи с УР у папки</td>
            <td>
                <code>git remote -v</code>
            </td>
            <td></td>
        </tr>
        <tr>
            <td>Связываем папку на гитхабе</td>
            <td><code>git remote add origin (ссылка на УР)</code></td>
            <td>Первую связку всегда называем <code>origin</code></td>
        </tr>
        <tr>
            <td>Удаление связки</td>
            <td><code>git remote remove origin</code></td>
            <td><code>origin</code> - название связки</td>
        </tr>
        <tr>
            <td>Забираем файлы из УР и обновляем в ЛР</td>
            <td><code>git pull origin main</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Отправка файлов в УР</td>
            <td><code>git push -u origin main</code></td>
            <td><code>main</code> - название основной ветки</td>
        </tr>
        <tr>
            <td>Переход в каталоге на ступень выше</td>
            <td><code>cd ..</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Переход в папку</td>
            <td><code>cd (название папки)</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Клонируем в выбранную папку файл из УР</td>
            <td><code>git clone (ссылка на УР) (название папки, если нужно ее создать)</code></td>
            <td>Ссылку копируем на Github</td>
        </tr>
    </tbody>
</table>
<table width="100%" border="1">
    <thead>
        <caption>
            <h3>Работа с ветками</h3>
        </caption>
    </thead>
    <tbody>
        <tr>    
            <th width="33%">Действие</th>
            <th width="33%">Комманда</th>
            <th width="33%">Комментарий</th>
        </tr>
        <tr>
            <td>Просмотре веток в ЛР</td>
            <td><code>git branch</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Создание ветки</td>
            <td><code>git branch (название ветки)</code></td>
            <td>Например, <code>new-branch</code></td>
        </tr>
        <tr>
            <td>Переключение на новую ветку</td>
            <td><code>git checkout (название ветки)</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Создание ветки с одновременным перключением на нее</td>
            <td><code>git checkout -b (название ветки)</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Отправка новой ветки в УР</td>
            <td><code>git push -u origin (название ветки)</code></td>
            <td></td>
        </tr>
        <tr>
            <td>Просмотр истории ветки</td>
            <td><code>git log (имя ветки) --graph --oneline</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
<table width="100%" border="1">
    <thead>
        <caption>
            <h3>Слияние веток</h3>
        </caption>
    </thead>
    <tbody>
        <tr>    
            <th width="33%">Действие</th>
            <th width="33%">Комманда</th>
            <th width="33%">Комментарий</th>
        </tr>
        <tr>
            <td>Заходим в ветку, В КОТОРУЮ будем делать слияние</td>
            <td><code>git checkout (название ветки)</code></td>
            <td>Например, <code>main</code></td>
        </tr>
        <tr>
            <td>Слияние веток</td>
            <td><code>git merge (название ветки, которую сливаем)</code></td>
            <td>Например, <code>new-branch</code></td>
        </tr>
        <tr>
            <td>Отправка ветки в УР</td>
            <td><code>git push</code></td>
            <td>Т.к. ветка уже существует, то не указываем <code>-u origin</code> <b><i>(название ветки)</i></b></td>
        </tr>
    </tbody>
</table>

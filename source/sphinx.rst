Sphinx
======

Создание проекта
----------------

1. Создайте новый проект, следуя подсказкам мастера

    .. code-block:: bash

        sphinx-quickstart

2. Отредактируйте ``conf.py`` по `инструкции <https://www.sphinx-doc.org/en/master/usage/configuration.html>`_

3. Запустите сервер

    .. code-block:: bash
        
        sphinx-reload .


Добавление страниц
------------------

В папке ``sources`` создайте страницы вашей документации в формате ``.rst``. В каждой папке должен находиться файл ``index.rst``, содержащий ссылки на остальные файлы.


Сборка статического сайта
-------------------------

Для сборки статического сайта выполните команду

    .. code-block:: bash

        sphinx-build -M html sourcedir outputdir

При наличии make-файла сборку можно запустить командой

    .. code-block:: bash
        
        make html


Добавление переводов
--------------------

1. Добавьте в ``conf.py`` следующие строки

    .. code-block:: python

        locale_dirs = ['locale/']
        gettext_compact = False

2. Запустите сборку в формат ``gettext``

    .. code-block:: bash

        make gettext

3. Сгенерируйте файлы локализации

    .. code-block:: bash

        sphinx-intl update -p _build/gettext -l en

4. Добавьте переводы строк в файлы локализации

5. Выполните сборку

    .. code-block:: bash
        
        make -e SPHINXOPTS="-D language='en'" html
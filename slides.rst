:title: Introducción a Git
:venue: 8va Jornadas de Software Libre de la UNNOBA
:author: Martín Gaitán
:css: slides.css


Introducción a Git
====================


.. image:: img/Git-Logo-1788C.png


Martín Gaitán / @tin_nqn_ / #8JSLUnnoba

--------

En el principio...
--------------------


El (des)control de versiones

.. image:: img/01-copies.png

.. note::

    * flujo totalmente lineal
    * impide colaboración
    * no hay historia.


--------

Algunos creyeron evolucionar
------------------------------

.. image:: img/dropbox.jpg

.. note::

     * soluciona la sincronizacion de la ultima versión
     * 1 copia

---

.. image:: img/meme1.jpg

---------

Lo

- ¡Rápido!
- Asegura integridad de datos
- Soporte robusto de miles de ramas paralelas
- Permite
- Totalmente distribuído
- Se banca proyectos como Linux :)

------

Instalación
-----------

**Windows **

http://code.google.com/p/msysgit

**Linux**

::
    [apt-get|] install git

**OS X**

::
    brew install git

--------

Configuración
-------------

*Quién sos*

.. code:: bash

    git config --global user.name "Martín Gaitán"
    git config --global user.email gaitan@gmail.com


*Tu editor*

.. code:: bash

    git config --global core.editor subl

--------

Empezando
----------

Crear un repo local

.. code:: bash

    git init

Luego se pueden declarar repos remoto

.. code:: bash

    git remote add origin https://github.com/mgaitan/intro-git.git

O directamente clonar un repositorio

.. code:: bash

    git clone https://github.com/mgaitan/intro-git.git .

--------

Creando *commits*
------------------

Cambios específicos

.. code:: bash

    git add README.txt
    git commit -m 'Contenido básico en el README'

O todos los cambios en archivos *trackeados*

.. code:: bash

    git commit -am 'El reactor nuclear funciona. Faltan tests del disparador'

---------

¿Dónde estoy?
--------------

.. code:: bash

    git status

.. code:: bash

    git log
    git log

.. code:: bash

    gitk

---------

Deshaciendo
-------------

Corregir el último commit


.. code:: bash

    git commit --amend

"Desagregar" (unstage)

.. code:: bash

    git reset HEAD file.py  # o bien
    git rm --cached file.py

Restaurar archivo (por defecto ``HEAD``)

.. code:: bash

    git checkout [rev] -- file.py

Revertir commit

.. code:: bash

    git revert 1776f5


--------

Borrando
---------

*Unstage* (quitar del proximo commit)

.. code:: bash

    git rm --cached file.py

Dejar de *trackear*:

.. code:: bash

    git rm file.py

------------

¿que diferencias hay?
----------------------

Cambios locales

.. code:: bash

    git diff

Cambios en stage

.. code:: bash

    git diff --cached

Respecto a una revision

.. code:: bash

    git diff 1776f5

Regalo de dios

.. code:: bash

    meld .

--------

.gitignore
----------

.. code:: bash

    $ cat .gitignore
    *.pyc
    *.swp
    /build/
    /doc/[abc]*.txt
    .pypirc
    *.egg-info

.. note::

    • Blank lines or lines starting with # are ignored
    • Standard glob patterns work
    • End pattern with slash (/) to specify a directory
    • Negate pattern with exclamation point (!)

---------

Repos remotos

Son

• Other clones of the same repository
• Can be local (another checkout) or remote (coworker, central server)
• There are default remotes for push and pull

$ git remote -v
origin git://github.com/schacon/ticgit.git (fetch)
origin git://github.com/schacon/ticgit.git (push)





Cada copia tiene **toda la historia**

- No **quebramos** si se muere el disco del servidor
- No **perdemos tiempo** en la red para ver la historia
- Podemos **trabajar offline** sin *commits-bomba*



revisar

http://www.gabrielsaldana.org/platica_git.pdf



http://dbrgn.ch/slides/20130207_getting_git/
http://www.slideshare.net/CarlosTaborda/why-git-sucks-and-youll-use-it-anyways
http://www.slideshare.net/leo.soto/introduccin-a-git
https://speakerdeck.com/schacon/introduction-to-git
http://www.slideshare.net/mickaeltr/git-github-leverage-your-open-source-projects
http://www.slideshare.net/anildigital/git-introduction


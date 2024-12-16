1. ### 
    ```

    ```



# 1.1 Repositorio Local 

1. ### Creamos o repositorio
    ```
    mkdir repositorio
    cd repositorio
    git init
    ```


1. ### Facemos os dous .txt
    ```
    echo "Son Carlos, son de Pontevedra e vivo en Santiago, teño 25 anos e estudo 1ºDAW" > carlos.txt
    echo "Das miñas actividades favoritas son os deportes, entre eles destacan o fútbol e o ciclismo. Tamén me encanta o automovilismo" > actividades.txt
    ```


1. ### Facemos o primeiro commit con `git add .` ( o "." engade todos os arquivos do directorio e subdirectorios) e `commit -m "comentario"`
    ```
    git add .
    git commit -m "primeiro commit"
    ```


1. ### Modificamos o arquivo con `nano` e volvemos a facer o `git commit -a -m ""` (a opción "-a" conforma os cambios en arquivos xa engadidos co `git add`, evitar ter que facelo cada vez antes do `git commit`)
    nano carlos.txt
    git commit -a -m "segundo commit"
    ```


1. ### Creamos o novo cartafol e arquivos
    ```
    mkdir cartafol1
    echo > cartafol1/archivo1.txt
    echo > cartafol1/archivo2.txt
    ```


1. ### Modificamos o arquivo con `nano`, creamos un arquivo gitignore e facemos un novo `git commit`
    ```
    nano actividades.txt
    echo "cartafol1/" > .gitignore
    git add .
    git commit -m "cuarto commit"
    ```


1. ### Comprobamos o historial de logs con `git log`   buscamos o hash do punto a restaurar. Facemos o `git checkout` para restaurar o punto anterior incluindo os 10 primeiros caracteres do hash
    ```
    git log
    git checkout 794ac4db96
    ```



# 1.2 Trabajando con repositorios locales

1. ### Creamos o cartafol e inicializamos o repositorio, despois con `ls -a` mostramos o contido (empregamos a opción `-a` para poder ver todos os arquivos e directorios, incluindo os ocultos)
    ```
    mkdir pagina_web
    cd pagina_web
    git init
    ls -a
    ```


1. ### Comprobamos o estado con `git status` (neste caso indica que estamos na rama master pero que aínda non hay arquivos engadidos nin cambios realizados)
    ```
    $ git status
    En la rama master
    No hay commits todavía
    no hay nada para confirmar (crea/copia archivos y usa "git add" para hacerles seguimiento)
    ```

1. ### Creamos o arquivo .html e facemos un `git commit`
    ```
    nano index.html
    git commit -m "Primeira páxina html"
    ```


1. ### Comprobamos o estado con `git status` (neste caso indica que o repositorio está completamente sincronizado)
    ```
    $ git status
    En la rama master
    nada para hacer commit, el árbol de trabajo está limpio
    ```


1. ### Modificamos o arquivo novamente e facemos un commit
    ```
    nano index.html
    git commit -a -m "cidades engadidas"
    ```


1. ### Mostramos o historial de commits con `git log`
    ```
    $ git log
    commit 746bec3917159a09bb411957c4853a68c0b1068e (HEAD -> master)
    Author: Carlos <1999cfo@gmail.com>
    Date:   Sun Dec 15 22:42:43 2024 +0100

        cidades engadidas

    commit d0968b1398c9dc4042f2b1ebc160ec88cfeac225
    Author: Carlos <1999cfo@gmail.com>
    Date:   Sun Dec 15 22:35:33 2024 +0100

        Primeira páxina html
    ```


1. ### Creamos os cartafoles e engadimos a información
    ```
    mkdir Oslo Venecia Kyoto
    nano Oslo/index.html
    nano Venecia/index.html
    nano Kyoto/index.html

    ```


1. ### Facemos o commit
    ```
    git add .
    git commit -m "Engadida información sobre cidades"
    ```


1. ### Mostramos o historial de cambios
    ```
    $ git log
    commit 7e1c41927893cba55cd7a5ba649afe893d79215e (HEAD -> master)
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 01:41:39 2024 +0100

        Engadida información sobre cidades

    commit 746bec3917159a09bb411957c4853a68c0b1068e
    Author: Carlos <1999cfo@gmail.com>
    Date:   Sun Dec 15 22:42:43 2024 +0100

        cidades engadidas

    commit d0968b1398c9dc4042f2b1ebc160ec88cfeac225
    Author: Carlos <1999cfo@gmail.com>
    Date:   Sun Dec 15 22:35:33 2024 +0100

        Primeira páxina html
    ```



# 1.3 Fundamentos de GIT

1. ### Creamos o cartafol, mostramos o contido e ccomprobamos o estado
    ```
    mkdir libro
    cd libro
    git init
    ls -a
    git status
    ```

    ```
    $ ls -a
    .  ..  .git

    $ git status
    En la rama master
    No hay commits todavía
    no hay nada para confirmar (crea/copia archivos y usa "git add" para hacerles seguimiento)
    ```


1. ### Creamos o arquivo ínidce e facemos un commit
    ```
    nano indice.txt
    git add .
    git commit -m "índice engadido"
    ```


1. ### Comprobamos o estado con `git status` (na rama master, encontrase todo sincronizado)
    ```
    $ git status
    En la rama master
    nada para hacer commit, el árbol de trabajo está limpio
    ```


1. ### Modificamos o arquivo con `nano` e facemos o commit e comprobamos o estado
    ```
    nano indice.txt
    git commit -a -m "Capitulo 4: La bella y la bestia"
    git status
    ```


1. ### Comprobamos o hsitorial con `git log`
    ```
    $ git log
    commit c766c40e05842a7c022fa1c4aa2beb2280366f13 (HEAD -> master)
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 01:56:24 2024 +0100

        Capitulo 4: La bella y la bestia

    commit 124aca14d7aac2e15e41149ccec8c7c353b68584
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 01:53:23 2024 +0100

        índice engadido
    ```


1. ###  Creamos o novo cartafol có novo documento
    ```
    mkdir capitulos
    echo "Y el lobo sopló y sopló y la casa derribó." > capitulos/capitulo2.txt
    ```


1. ### Facemos o commit
    ```
    git add .
    git commit -m "Añadido capitulo 2"
    ```


1. ### Mostramos o historial
    ```
    $ git log
    commit daf6cc246a1247f6e16f27ca7ecb80ec2f4a2864 (HEAD -> master)
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 02:01:06 2024 +0100

        Añadido capitulo 2

    commit c766c40e05842a7c022fa1c4aa2beb2280366f13
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 01:56:24 2024 +0100

        Capitulo 4: La bella y la bestia

    commit 124aca14d7aac2e15e41149ccec8c7c353b68584
    Author: Carlos <1999cfo@gmail.com>
    Date:   Mon Dec 16 01:53:23 2024 +0100

    ```


1. ### Creamos o novo arquivo
    ```
    echo "Abuelita qué ojos más grandes tienes." > capitulos/capitulo3.txt
    ```


1. ### Mostramos o estado do repositorio de forma abreviada coa opción `-s` sendo `git status -s` as opcions son:
    > ?? -> Arquivo non ratrexado

    > A  -> Arquivo engadido

    > M  -> Arquivo modificado

    ```
    $ git status -s
    ?? capitulos/capitulo3.txt
    ```


1. ### Modificamos novamente o arquivo e creamos o `.gitignore` para o arquivo `capitulo3.txt`
    ```
    nano indice.txt
    echo "capitulos/capitulo3.txt" > .gitignore

    ```


1. ### Facemos o commit
    ```
    git add .
    git commit -m ".gitignore e índice capítulo 5"

    ```


1. ### Modificamos o `.gitignore` 
    > para que ignore todos os arquivos que comencen por "_" 
    >>(engadindo no texto do arquivo "\_*")
    
    >poñemos a excepción do arquivo "_ayuda.txt" 
    >>(facémolo engadindo "!_ayuda.txt" no texto do arquivo)

    ```
    nano .gitignore 
    ```


1. ### Creamos of ficheiros con "_"
    ```
    echo "Fichero para almacenar logs" > _logs.txt
    echo "Fichero de ayuda." > _ayuda.txt

    ```


1. ### Engadimos todos os arquivos e facemos o commit
    > `git add .` engade todos os novos arquivos que non esten incluidos no .gitignore salvo as excepcións

    > no commit sincronizanse todos os arquivos que non están no .gitignore salvo as excepcións

    ```
    git add .
    git commit -m "Añadidos archivos de ayuda y logs"

    ```


1. ### Modificamos o arquivo con `nano`
    ```
    nano capitulos/capitulo2.txt
    ```


1. ### Comprobamos el estado (en este caso indica que hay cambios en capitulo2.txt que no fueron sincronizados)
    ```
    $ git status
    En la rama master
    Cambios no rastreados para el commit:
    (usa "git add <archivo>..." para actualizar lo que será confirmado)
    (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
            modificados:     capitulos/capitulo2.txt

    sin cambios agregados al commit (usa "git add" y/o "git commit -a")
    ```


1. ### Realizamos o commit
    ```
    git add .
    git commit -m "Capitulo 2 modificado"

    ```


1. ### Voltamos a modificar o arquivo, miramos o estado abreviado con `git status -s` e vemos os cambios non preparados con `git diff`
    ```
    nano  capitulos/capitulo2.txt

    $ git status -s
     M capitulos/capitulo2.txt
    ```

    ```
    $ git diff
    diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
    index 754d80c..ec80859 100644
    --- a/capitulos/capitulo2.txt
    +++ b/capitulos/capitulo2.txt
    @@ -1,2 +1,3 @@
    -Caperucita iba por el bosque 
    -con su capa roja 
    +Caperucita iba por el bosque con su capa roja 
    +cuando llegó a casa de su abuela le dijo 
    +"Abuela qué ojos más grandes tienes"
    ```
    (pon counha liña "-" e en vermello as partes borradas e cun "+" e en verde as novas partes)


1. ### Eliminamos o arquivo "_ayuda.txt", modificamos o nome de "indice.txt" e facemos o commit final
    ```
    git rm _ayuda.txt
    git mv indice.txt indice_libros.txt
    git add .
    git commit -m "último commit"
    ```


# 2 Ramas GIT

1. ### Creamos a nova rama con `git branch nome_da_rama`
    ```
    git branch bibliografia
    ```


1. ### Mostramos as ramas con `git branch`
    ```
    $ git branch
    bibliografia
    * master
    ```


1. ### Cambiamos á rama "bibliografia" con `git checkout` e creamos o novo arquivo e facemos o commit
    ```
    git checkout bibliografia
    echo "caperucita roja, Trina Schart Hyman, Charles Perrault" > bibliografía.txt
    git add .
    git commit -m "Añadida primera referencia bibliográfica"

    ```


1. ### Cambiamos á rama `master` e fusionamos as ramas con `git merge`
    ```
    git checkout master
    git merge bibliografia
    ```

    ```
    $ git merge bibliografia
    Actualizando 08d1351..68405fd
    Fast-forward
    "bibliograf\303\255a.txt" | 1 +
    1 file changed, 1 insertion(+)
    create mode 100644 "bibliograf\303\255a.txt"
    ```


1. ### Eliminamos a ramo con `git branch -d nome_da_rama`
    ```
    $ git branch -d bibliografia
    Eliminada la rama bibliografia (era 68405fd).
    ```


1. ### Con `git checkout -b nome_da_rama` creamos a nova rama e cambiamos a ela, modificamos o arquivo e facemos o commit
    ```
    git checkout -b harrypotter
    nano bibliografia.txt
    git add .
    git commit -m "Añadida bibliografía de harry potter"

    ```


1. ### Cambiamos á rama `master`, modificamos "bibliografia.txt" e fusionamos as ramas.
    ```
    git checkout master
    nano bibliografia.txt
    git merge harrypotter

    ```

    ```
    $ git merge harrypotter
    Actualizando 68405fd..d590180
    error: Los cambios locales de los siguientes archivos serán sobrescritos al fusionar:
            bibliografía.txt
    Por favor, confirma tus cambios o aguárdalos antes de fusionar.
    Abortando
    ```
    (ao tentar facer a fusion danos o erro de que temos cambios locais non confirmados)


1. ### Fago un commit pero segue dando problemas
    ```
    $ git add .
    git commit -m "Cambios locales en bibliografía.txt"
    
    $ git merge harrypotter
    Auto-fusionando bibliografía.txt
    CONFLICTO (contenido): Conflicto de fusión en bibliografía.txt
    Fusión automática falló; arregle los conflictos y luego realice un commit con el resultado.
    ```


1. ### Comprobamos o estado (na que indica que o arquivo foi modificado por ambos)
    ```
    $ git status
    En la rama master
    Tienes rutas no fusionadas.
    (arregla los conflictos y ejecuta "git commit"
    (usa "git merge --abort" para abortar la fusion)

    Rutas no fusionadas:
    (usa "git add <archivo>..." para marcar una resolución)
            modificados por ambos:  "bibliograf\303\255a.txt"

    sin cambios agregados al commit (usa "git add" y/o "git commit -a")
    ```


1. ### Comprobamos o arquivo con `nano` e gardamos o contido que queiramos
    ```
    nano bibliografía.txt

    caperucita roja, Trina Schart Hyman, Charles Perrault
    <<<<<<< HEAD
    El Rey León, Rob Minkoff, Roger Allers
    =======
    Harry Potter y la piedra filosofal, J. K. Rowling
    Harry Potter y el cáliza de fuego, J. K. Rowling
    >>>>>>> harrypotter
    ```


1. ### Por último facemos a resolucion dos conflictos e o commit
    ```
    git add .
    git commit -m "resolución final.txt"
    ```



# 3 Repositorios remotos GIT


1. ### Imos a "github" e creamos un novo repositorio


1. ### Engadimos o repositorio remoto ó local con `git remote add origin url`
    ```
    git remote add origin https://github.com/caarlosf/libro2-git.git
    ```


1. ### Verificamos a conexión do remoto con `git remote -v`
    ```
    $ git remote -v
    origin  https://github.com/caarlosf/libro2-git.git (fetch)
    origin  https://github.com/caarlosf/libro2-git.git (push)
    ```


1. ### Subimos o contido ó remoto con `git push -u origin master`
    ```
    git push -u origin master
    Enumerando objetos: 38, listo.
    Contando objetos: 100% (38/38), listo.
    Compresión delta usando hasta 4 hilos
    Comprimiendo objetos: 100% (28/28), listo.
    Escribiendo objetos: 100% (38/38), 3.45 KiB | 588.00 KiB/s, listo.
    Total 38 (delta 9), reusados 0 (delta 0), pack-reusados 0
    remote: Resolving deltas: 100% (9/9), done.
    To https://github.com/caarlosf/libro2-git.git
    * [new branch]      master -> master
    rama 'master' configurada para rastrear 'origin/master'.
    ```


1. ### Como non aparecen todos os cartafoles vou ó primeiro cartafol e fago un commit dende el
    ```
    git add .
    git commit -m "todo"
    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```


1. ### 
    ```

    ```





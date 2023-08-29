cd# Instalar dependecias para compilar en C y C++
How to Install build-essential on Ubuntu
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential
```
Paginas de manual.
```bash
sudo apt install manpages-dev
```
Para ver que versión se instalo.
```bash
gcc --version
g++ --version
```

Instalar clang y clang-format

-----------------------------------------------------------------------------
# Intalar Neovim.
```bash
sudo apt-get update
sudo apt-get install neovim
```

- Para que funcione las variables F4

    ```bash
    sudo apt-get install exuberant-ctags
    ```
    Para ir a la definicion de la funcion poner en terminal:
    ```bash
    ctags -R .      // se crea un archivo de direciones
    ```
    tocar la tecla `ctrl+]`. O se puede usar el siguiente comando para saltar a la definición de la función: `:tag my_function`

Ahora vamos a agregar iconos a vim para cuando se toca F3
1. Vamos a la página. Descargamos el zip de iconos que mas nos guste.
    ```bash
    https://www.nerdfonts.com/
    ```
2. Movemos el zip a la carpeta `~/.local/share/fonts/ ` si no esta creada la creamos. Lo podemos hacer manual o usamos el siguiente comando.
    ```bash
    mkdir -p ~/.local/share/fonts/ 
    ```
3. Para mover el archivo zip con comandos.
    ```bash
    cp ~/Descargas/3270.zip ~/.local/share/fonts/
    ```
4. Vas a la carpeta `~/.local/share/fonts/`, ejecutas el siguiente comando y listo. Cerrar todo para para que los cambios sean afectivos.
    ```bash
    fc-cache -fv
    ```
    
5. Como installar github copilot en neovim
    Primer tener instalado `Nodejs`. link -> [Nodejs]
    ```bash
    curl -fsSL https://deb.nodesource.com/setup_19.x | sudo -E bash - &&\
    sudo apt-get install -y nodejs
    ```
    Fuente:
        https://www.youtube.com/watch?v=OMhMnj7SBRQ
        
6. Instalamos Github copilot. link -> [Copilot]
    ```bash
    git clone https://github.com/github/copilot.vim \
   ~/.config/nvim/pack/github/start/copilot.vim
   
   :Copilot setup
   :Copilot enable
    ```
7. Auto completado con coc
    Colocar esto en el init.vim e instalarlo.
    ```
    Plug 'neoclide/coc.nvim', {'branch': 'release'}
    ```
    Primero instalar la ultima version de de nodejs
    ```
    curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - &&\
    sudo apt-get install -y nodejs
    ```
    eso es todo.
-----------------------------------------------------------------------------
# Intalar Terminator.
- Installar terminator.
```bash
sudo apt install terminator

```
Para crear un short cup (atajo de teclado). Vamos al icono de `inicio` y buscamos `Teclado`, ` Añadir un atajo personalizado` y colocamos un nombre descriptivo cualquiera y el nombre del programa en minucula: orden `terminator`.

- Para agregar terminator al menu del segundo click ***( add "Open in Terminator" in your right-click menu)***. ver liink -> [Terminar-]
    1. ir al directorio `/home/$USER/.local/share/nemo/actions`
    2. crear el archivo `open_in_terminator.nemo_action file`
    ```
    [Nemo Action]

    Name=Open in Terminator
    Comment=Open the 'terminator' terminal in the selected folder
    Exec=terminator --working-directory="%F"
    Icon-Name=terminator
    Selection=any
    Extensions=dir;
    ```
    Fuente:
    https://unix.stackexchange.com/questions/336368/how-to-configure-nemos-right-click-open-in-terminal-to-launch-gnome-terminal

---------------------------------------------------------------------------------------------------
# Bashrc
Agregamos el git branch a la terminal.
```bash
function parse_git_branch {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/[\1]/'
}
PS1='\[\e[0;1;32m\]\u\[\e[0;1;32m\]@\[\e[0;1;32m\]\H\[\e[0;1;32m\]:\[\e[0;1;34m\]\w:\[\e[0;1;33m\]$(parse_git_branch)\[\e[0m\]\$ \[\e[0m\]'

# Nota '34m]\w \' elimino el espacio entre w -> '34m]\w\' 
```

-----------------------------------------------------------------------------
# Esplorador de archivos (File explorer) - RANGER
* Ejecutas en las terminal. link -> [ranger]
```bash
sudo apt install ranger
```
NOTA: ver man ranger para como desplazarse por el explorador.

* Para poder eliminar archivos con el File explorer ranger:
Crea los archvios de configuracion en defaul.
```bash
ranger --copy-config=all
```
Dentro del archivo escribimos, renplazar `${USER}` por nombre de usuario.
```bash
map DD shell mv %s /home/${USER}/.local/share/Trash/files/
map DD shell gio trash %s
```
* Agregar a Ranger iconos - Ranger-Devicoins [ranger-devicoins].
Solo seguir las intruciones.
```bash
git clone https://github.com/alexanderjeurissen/ranger_devicons ~/.config/ranger/plugins/ranger_devicons
```
Abris el archivo `rc.conf` y coocas `default_linemode devicons` o haces
```bash
echo "default_linemode devicons" >> $HOME/.config/ranger/rc.conf
```

* Fuente:
    https://www.youtube.com/watch?v=aAeJhWtqlgY
    https://vitux.com/how-to-install-ranger-terminal-file-manager-on-linux/
    https://wiki.archlinux.org/title/ranger     // ENG Como add eliminate file
    https://wiki.archlinux.org/title/Ranger_(Espa%C3%B1ol)  // ESPAÑOL
    

-----------------------------------------------------------------------------
# Clang Format - Identar automaticamente el codigo.
```bash
sudo apt install clang
sudo apt install clang-format
```
Para aplicarlo en un archivo hacemos.
```bash
clang-format file > formattedfile
clang-format -i my_program.c
```
- fuente:
    https://askubuntu.com/questions/448497/source-code-formatter-indenter

-----------------------------------------------------------------------------
# Bat vs Cat.
Pagina oficial en git. link -> [bat]
```bash
sudo apt install bat
```
Ahora para ejecutar el comando tenemos que usar `batcat my_program.c`, vamos agregar un alias para acortalo a `batcat my_program.c`.
Vamos al archivo `.bashrc` agremos al final. y listo. 
```bash
# FERNANDO
# Alias para Bat vs cat
alias bat='batcat --paging=never'
```

-----------------------------------------------------------------------------
# Git comandos basicos.
- Ver la configuracion de git
```git
git config --list
```
- Abrir el archivo de configracion de git
```git
git config --global --edit
```
- Editar usuario e email
```git
git config --global user.name lcondoriz
git config --global user.email lcondoriz@fi.uba.ar
```

## Conexion SHH (para no tener que poner cosntantemente la contreseña)
* En la terminal, carpeta home.
```git
ssh-keygen -t ed25519 -C "lcondoriz@fi.uba.ar"
```
* Agregar tu clave SSH al ssh-agent.
```git
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
-----------------------------------------------------------------------------
## Compilar y debuggear en Visual studio code C/C++
Combiene instalar la extensión `Makefile Tools` [MakefileTools]. Lo que hace es tomar el archivo make y usarlo para debugear y compilar.

-----------------------------------------------------------------------------
# Citas link
- [bat]: <https://github.com/sharkdp/bat>
- [ranger]: <https://github.com/ranger/ranger>
- [ranger-devicoins]: <https://github.com/alexanderjeurissen/ranger_devicons>
- [Nodejs]: <https://github.com/nodesource/distributions/blob/master/README.md#debinstall>
- [Copilot]: <https://docs.github.com/en/copilot/getting-started-with-github-copilot?tool=neovim>
- [MakefileTools]: <https://devblogs.microsoft.com/cppblog/now-announcing-makefile-support-in-visual-studio-code/>


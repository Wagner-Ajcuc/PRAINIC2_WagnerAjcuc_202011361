
# Manual de Instalación de Ubuntu LTS en VirtualBox y Uso de Comandos Básicos en la Terminal

---

## 1. Instalación de Ubuntu LTS en VirtualBox

### Requisitos previos
- Descargar e instalar **VirtualBox** desde: [https://www.virtualbox.org](https://www.virtualbox.org)
- Descargar la ISO de **Ubuntu LTS** desde: [https://ubuntu.com/download](https://ubuntu.com/download)

### Pasos de instalación
1. Abrir VirtualBox y hacer clic en **Nueva**.
2. Configurar:
   - Nombre: `Ubuntu LTS`
   - Tipo: `Linux`
   - Versión: `Ubuntu (64-bit)`
3. Asignar memoria RAM (mínimo 2GB recomendado).
4. Crear un disco duro virtual (VDI, tamaño dinámico, mínimo 20GB).
5. Ir a **Configuración → Almacenamiento** y seleccionar la ISO de Ubuntu como disco óptico.
6. Iniciar la máquina virtual.
7. Seguir el instalador de Ubuntu:
   - Elegir idioma.
   - Conectarse a red (opcional).
   - Seleccionar **Instalación normal**.
   - Crear usuario y contraseña.
8. Finalizar instalación y reiniciar.

---

## 2. Introducción a la Terminal en Ubuntu

La terminal es la herramienta más poderosa de Ubuntu. Con ella puedes gestionar archivos, programas y configuraciones del sistema.

A continuación, se explican los **comandos fundamentales** con ejemplos.

---

## 3. Comandos básicos de navegación y gestión

### 3.1 Navegar entre archivos y directorios
- `pwd` → Muestra la ruta actual.  
  ```bash
  pwd
  # /home/usuario
  ```

- `cd` → Cambiar de directorio.  
  ```bash
  cd Documentos
  cd ..
  cd /home/usuario/Descargas
  ```

---

### 3.2 Ver el contenido de un directorio
- `ls` → Lista los archivos.  
  ```bash
  ls
  ls -l     # Detallado
  ls -a     # Incluye archivos ocultos
  ls -lh    # Tamaños legibles
  ```

---

### 3.3 Crear carpetas en un directorio
- `mkdir` → Crear carpeta.  
  ```bash
  mkdir proyectos
  mkdir -p proyectos/java   # Crea subdirectorios
  ```

---

### 3.4 Copiar archivos y carpetas
- `cp` → Copiar archivos.  
  ```bash
  cp archivo.txt /home/usuario/Documentos/
  cp -r carpeta /home/usuario/Escritorio/
  ```

---

### 3.5 Mover archivos y carpetas
- `mv` → Mover o renombrar.  
  ```bash
  mv archivo.txt /home/usuario/Descargas/
  mv viejo.txt nuevo.txt
  ```

---

### 3.6 Eliminar archivos y carpetas
- `rm` → Eliminar.  
  ```bash
  rm archivo.txt
  rm -r carpeta/    # Elimina carpeta con contenido
  rm -rf carpeta/   # Forzar borrado (peligroso)
  ```

---

### 3.7 Ingresar como superusuario
- `sudo` → Ejecutar con permisos de administrador.  
  ```bash
  sudo apt update
  sudo rm archivo.txt
  ```

- `su` → Cambiar a superusuario (requiere contraseña root).  
  ```bash
  su
  ```

---

### 3.8 Actualizar permisos de archivos o directorios
- `chmod` → Cambiar permisos.  
  ```bash
  chmod 755 script.sh
  chmod u+x archivo.sh
  ```

- `chown` → Cambiar propietario.  
  ```bash
  sudo chown usuario archivo.txt
  ```

---

### 3.9 Crear/editar un archivo de texto desde la terminal
- Con **nano**:  
  ```bash
  nano archivo.txt
  ```

- Con **vi/vim**:  
  ```bash
  vi archivo.txt
  ```

- Crear vacío:  
  ```bash
  touch archivo.txt
  ```

---

### 3.10 Instalar paquetes
- Usando `apt`:  
  ```bash
  sudo apt install vim
  sudo apt install git
  ```

---

### 3.11 Actualizar paquetes
- Actualizar lista y sistema:  
  ```bash
  sudo apt update    # Actualiza lista de paquetes
  sudo apt upgrade   # Instala actualizaciones
  ```

---

### 3.12 Eliminar paquetes
- Eliminar programa:  
  ```bash
  sudo apt remove vim
  ```

- Eliminar con configuración:  
  ```bash
  sudo apt purge vim
  ```

- Limpiar dependencias:  
  ```bash
  sudo apt autoremove
  ```

---

## 4. Ejemplo práctico: Instalación y configuración de Apache2

Este ejemplo muestra cómo aplicar varios de los comandos vistos para instalar, configurar y ejecutar el servidor web Apache2 en Ubuntu.

### 4.1 Instalar el servidor web Apache2
```bash
sudo apt update
sudo apt install apache2
```

### 4.2 Verificar que el servicio esté activo
```bash
sudo systemctl status apache2
```
- Abrir navegador en: [http://localhost](http://localhost) y comprobar la página por defecto.

### 4.3 Cambiar el puerto por defecto
- Modificar archivos:
  - `/etc/apache2/ports.conf`
  - `/etc/apache2/sites-available/000-default.conf`

Configurar para usar el puerto **8080** en lugar del 80.

### 4.4 Modificar la página de Apache
Acceder al directorio `/var/www/html/` y modificar el archivo `index.html` con el nombre y número de carné.

### 4.5 Mostrar la página con los cambios
```bash
sudo systemctl restart apache2
```
Abrir navegador en: [http://localhost:8080](http://localhost:8080)

---

## 5. Conclusión

Con este manual aprendiste:
- A instalar Ubuntu LTS en VirtualBox.
- A navegar y manipular archivos desde la terminal.
- A gestionar permisos y paquetes del sistema.
- A instalar y configurar Apache2 como ejemplo práctico.

Dominar estos comandos es fundamental para el trabajo en servidores y máquinas en la nube.

---

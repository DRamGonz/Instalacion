# 🚀 Manual de Instalación de Entorno de Desarrollo (Linux)

Este manual explica cómo instalar y configurar **Apache, PHP, MySQL, Composer y Node.js** en un sistema Linux desde cero. Ideal para trabajar con **Laravel + Tailwind + JavaScript**.

---

## 📦 Actualizar el sistema

```bash
sudo apt update && sudo apt upgrade -y && sudo appt autoremove -y && sudo at autoclean 
```

---

## 🌐 Instalar Apache

```bash
sudo apt install apache2 -y
```

- Verificar que funciona: abre en tu navegador `http://localhost` → debe mostrar la página de Apache.
- Para manejar Apache:

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
sudo systemctl status apache2
```

---

## 🐘 Instalar PHP (con extensiones comunes para Laravel)

```bash
sudo apt install php libapache2-mod-php php-mysql php-cli php-mbstring php-xml php-bcmath unzip curl -y
```

- Ver versión instalada:

```bash
php -v
```

---

## 🛢️ Instalar MySQL

```bash
sudo apt install mysql-server -y
```

- Asegurar la instalación:

```bash
sudo mysql_secure_installation
```

- Ingresar a MySQL:

```bash
sudo mysql -u root -p
```
---

## 🎼 Instalar Composer (gestor de dependencias PHP)

```bash
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
```

- Verificar:

```bash
composer -V
```

---

## ⚡ Instalar Node.js y npm

Recomendado instalar con **nvm** (Node Version Manager):

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
source ~/.bashrc
```

- Instalar la última versión LTS de Node:

```bash
nvm install --lts
```

- Verificar versiones:

```bash
node -v
npm -v
```

---

## 🎨 Instalar TailwindCSS (cuando tengas tu proyecto listo)

Dentro de tu proyecto:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init
```

---

## 🖥️ Instalar Laravel (vía Composer)

```bash
composer global require laravel/installer
```

Agregar el binario de Composer al PATH (en `~/.bashrc` o `~/.zshrc`):

```bash
export PATH="$HOME/.config/composer/vendor/bin:$PATH"
```

Crear un nuevo proyecto:

```bash
laravel new proyecto
```

O usando Composer directamente:

```bash
composer create-project laravel/laravel proyecto
```

---

## ✅ Verificación final

- Apache funcionando en `http://localhost`.
- PHP probado con:

```bash
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
```

- MySQL accesible con `mysql -u root -p`.
- Node y npm listos (`node -v && npm -v`).
- Composer instalado (`composer -V`).
- Laravel funcionando (`php artisan serve`).

---

## 🎉 Listo para programar

Ya tienes un entorno con **PHP, Apache, MySQL, Node.js, Composer y Laravel** funcionando en tu Linux. 🚀

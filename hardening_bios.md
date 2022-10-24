author: Juan Ramón González Hurtado
summary: Guía para bastionado de BIOS/UEFI
id: hardening_guia_BIOS
categories: codelab,markdown 
environments: Web 
status: Published 

 

# Bastionado de BIOS/UEFI



## Establecemos contraseñas

Para entrar en la BIOS reiniciamos nuestro sistema y pulsamos repetidamente la tecla suprimir.
Una vez, en la BIOS entramos en el menú de Seguridad:

<p>![menu_seguridad](hardening_guia_BIOS/img/capturamenuseguridad.bmp)</p>

### Contraseña de administrador de BIOS

Ahora vamos a establecer una contraseña para el administrador de la BIOS, de esta manera evitaremos que cualquiera que entre en la BIOS pueda modificar ciertos parámetros que pueden comprometer nuestro sistema.

<p> Seleccionamos la opción de <b> Administrator Password </b> </p>

<p>![admin_password](hardening_guia_BIOS/img/pwdadminBIOS.bmp)</p>

### Contraseña de usuario o Power-On

Establecemos una contraseña para el arranque del sistema, añadiendo otra capa de seguridad más:

<p> Seleccionamos la opción de <b> User Password </b> </p>


<p>![user_password](hardening_guia_BIOS/img/pwduserBIOS.bmp)</p>

## Opciones de arranque y permisos

En este apartado vamos a ver cómo podemos configurar los permisos para evitar el arranque desde dispositivos no autorizados y en su defecto modificar el orden del arranque de manera que sea lo más segura posible.

### Evitando el arranque desde dispositivos externos

Modificaremos los permisos de manera que sólo sea posible realizar el arranque desde el disco duro, dejando "Disabled" el resto de dispositivos:

<p>![permiso_usb](hardening_guia_BIOS/img/usbpermissiondenied1.bmp)</p>

<p>El resultado sería el siguiente:</p>

<p>![permiso_usb2](hardening_guia_BIOS/img/usbpermissionremoved.bmp)</p>

### Orden de arranque seguro

Vamos a evitar el arranque desde dispositivos priorizando el disco duro de nuestro sistema, de esta manera, mientras esté conectado nuestro disco duro, no podrán realizarse arranques desde dispositivos externos en caso de que tengan alguna clase de permiso para ello.

<p> En primer lugar, pondremos nuestro disco duro, luego seleccionaremos el resto de dispositivos en el siguiente orden: </p>

<p>![orden_arranque](hardening_guia_BIOS/img/ordenarranque.bmp)</p>

## Otras opciones de seguridad

En este apartado analizaremos otras opciones de seguridad como es el <b>Secure Boot</b>.

<p>Secure Boot es una herramienta de seguridad que viene incluída en UEFI, y que impide la ejecución de software no firmado o certificado en el arranque del sistema. De esta manera nuestro PC arrancará sólo con software de confianza del OEM (fabricante de equipos originales)</p>

<p>Podemos usarlo simplemente como otra capa de seguridad en nuestro bastionado de la BIOS</p>

<p>A continuación veremos dónde podemos habilitarlo, aunque por defecto estará habilitado. Si no lo está habilitado lo habilitaremos dejando "Enabled" el <b>Secure Boot Support:</b></p>

<p>![secure_boot](hardening_guia_BIOS/img/securebootactive.bmp)</p>

<p> También existe la opción de personalizar el <b>Secure Boot</b> con otras claves de arranque seguro. </p>

![](https://raw.githubusercontent.com/lexielex/ManualRP/imagenes/presidencia1.png) 
![](https://raw.githubusercontent.com/lexielex/ManualRP/imagenes/mx_d-logos1.png)

## RapidPro como Servicio
***

#### RapidPro: ¿Qué es y qué puede hacer?
Es una plataforma inteligente y de código abierto, que utiliza una interface visual de uso fácil que permite rápidamente generar flujos de comunicación entre gobierno y ciudadanos.
Con RapidPro se pueden enviar mensajes de dos vías personalizados, focalizados y oportunos a través de SMS, Facebook, Telegram y/o Twitter. 

Algunos usos prácticos de **RapidPro** son:
| Funcionalidad|  | Ejemplo |
|:---------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Mensajes personalizados | Los mensajes se adaptan a las necesidades del usuario en el tiempo, considerando datos existentes e información nueva capturada a través de los mensajes | Pueden incluir información específica a la beneficiaria, como puede ser su nombre, su fecha de próxima consulta en un médico. |
| Mensajes focalizados | La plataforma puede enviar mensajes específicos a grupos segmentados | Beneficiarios con una denuncia registrada previamente vs. nuevos usuarios |
| Mensajes oportunos | Se puede programar el envío de mensajes en momentos específicos para producir el efecto deseado | Envío de recordatorio automático el día antes de que un derechohabiente tenga que ir a una capacitación |
| Mensajes con servicios web | Además de SMS RapidPro permite el envío de mensajes en Telegram, Facebook Messenger y Twitter | Conectar RapidPro a la página de Facebook existente, para que los usuarios puedan comenzar un flujo de mensajes ahí mismo |
| Perfiles y permisos | Permite generar permisos distintos para perfiles diferentes dentro de la dependencia (Administrador, Editor o Visualizador) | Si la dependencia quiere que solo parte del equipo interno edite flujos de mensajes y otra parte pueda solo ver pero no modificar información |
| Cómputos y cálculos internos | Permite hacer cómputos y cálculos dentro de los flujos para personalizar los SMS | Se pregunta el peso y altura de un paciente y calcula el índice de masa corporal |
| Conexión con fuentes externas y otras bases de datos (webhooks) | La plataforma puede sacar datos de una base alojada en otra URL o enviar información a fuentes externas | Saca cuándo y dónde un derechohabiente recibirá el siguiente apoyo con solo preguntar su CURP y envía un recordatorio automático. Autollenado de una encuesta en un formulario externo con la información de las respuestas enviadas por SMS |
| Detona otros servicios | Permite que un mensaje detone otros servicios, como correo electrónico, SMS a otra persona o llamadas telefónicas | Que el envío de la palabra “alerta” detone una llamada a servicios de emergencia para adultos mayores |
| Facilita captura y descarga de información recolectada | Guardar información deseada de respuestas en una base de datos que es fácilmente descargable (.csv o con la API) | Generar una columna llamada “vitaminas” para aquellos usuarios que respondan sí cuándo se les pregunte si toman vitaminas diario |

#### Guía de uso
***
1. [Cuentas y permisos](#1-cuentas-y-permisos)
    + Tu cuenta: cómo crearla y en dónde editarla
	+ Perfiles y permisos de usuarios
2. [Canales](#2_canales)
    + Agregar y quitar canales
    + Tipos de canales:
        + Android
        + Agregador
        + Números virtuales (Twilio, Nexmo)
3. [Mensajes y flujos](#3_mensajes)
    + Mensajes:
        + Manejo de mensajes: Archivar, Exportar, Marcar, Borrar
        + Agendar un mensaje para envío en otro momento
    + Flujos:
        + Tipos de flujos
        + Manejo de flujos: Crearlos y editarlos
        + Agregar y actualizar contactos dentro de un flujo
        + Detonar otros servicios dentro de un flujo
        + Webhooks
        + Cómo importarlos y exportarlos
4. [Contactos](#4_contactos)
    + Crear contactos
    + Editar contactos
    + Manejo de valores dentro de contactos
    + Importar y exportar contactos
    + Grupos de contactos: 
        + ¿Cómo crear y editar un grupo?
        + ¿Cómo agregar contactos a un grupo?
5. [Campañas](#5_campañas)
    + Campañas: crearlas, editarlas y archivarlas
6. [Triggers](#6_triggers)
    + Palabras clave para empezar flujos
    + Ignorarar palabras clave dentro de un flujo
7. [Servicios Web](#7_web)
    + Facebook
    + Telegram
    + Twitter

### 1 Cuentas y permisos
***
##### _Cuentas: cómo crearlas y en dónde editarlas_
El equipo de la CEDN creeará una cuenta para tu organización y agregará a la persona designada como administrador. Después de recibir el correo de RapidPro, da clic en el link para aceptar la invitación para formar parte de la organización creada para tu proyecto en la plataforma 

![](https://raw.githubusercontent.com/lexielex/ManualRP/imagenes/1invitacionRP.png)

Una vez dentro de RapidPro, puedes ir la página de tu cuenta para:
   + Ver tus créditos disponibles o comprar créditos
   + Ver, agregar o borrar canales 
   + Editar el nombre de tu organización
   + Cambiar zona horaria y formato de fecha
   + Establecer el idioma primario y agregar otros idiomas
   + Configurar Webhooks que se comuniquen con aplicaciones externas
   + Manejar perfiles de usuarios (para administradores)
![](https://raw.githubusercontent.com/lexielex/ManualRP/imagenes/2account.png)

##### _Perfiles y permisos de usuarios_
Hay cuatro tipos de perfiles:

+ *Surveyors*: no tienen provilegios administrativos, ni pueden accesar la cuenta del equipo. Solo pueden enviar información via la applicación móvil RapidProSurveyor
+ *Viewers*: pueden ver información de contactos, flujos y resultados, pero no pueden modificar nada.
+ *Editores*: pueden hacer todo lo anterior, y también pueden editar, enviar mensajes, iniciar flujos, e importar/exportar flujos y sus resultados. 
+ *Administradores*: pueden hacer todo lo que hacen los editores, y aparte pueden hacer cambios a perfiles de cuentas y canales

Para administradores, los perfiles existentes aparecerán en la página de la cuenta, debajo de la sección de configuración de Webhooks.

![](https://github.com/lexielex/ManualRP/blob/imagenes/3perfiles_1.png?raw=true)

Da clic ahí para:
+ Invitar a nuevos usuarios y asignares un rol
+ Ver usuarios existentes y sus permisos
+ Editar permisos de usuarios existentes
+ Borrar usuarios de tu organización

![](https://github.com/lexielex/ManualRP/blob/imagenes/4perfiles2.png?raw=true)

### 2 Canales
_Agregar y quitar canales_

_Tipos de canales_
+ Android
+ Agregador
+ Números virtuales (Twilio, Nexmo)

### 3 Mensajes y flujos
_Mensajes_
+ Manejo de mensajes: Archivar, Exportar, Marcar, Borrar
When entering your content into a message action, keep in mind that messages exceeding 160 characters will be sent as two messages. We provide a character counter beneath the message input of each message action to help you keep track: 

+ Agendar un mensaje para envío en otro momento

_Flujos_
+ Tipos de flujos
+ Manejo de flujos: Crearlos y editarlos
+ Agregar y actualizar contactos dentro de un flujo
+ Detonar otros servicios dentro de un flujo
+ Webhooks
+ Cómo importarlos y exportarlos








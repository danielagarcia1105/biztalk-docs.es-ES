---
title: Configuración del adaptador de FTP | Microsoft Docs
ms.custom: ''
ms.date: 09/28/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters, configuring
- configuring [FTP adapters]
ms.assetid: 7e7d2e2d-142e-4459-be25-efd501b396d2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f81353597bf836c2032b8ad79cb1c779749ed6fc
ms.sourcegitcommit: c1e83b63ae34bd586e6e0ccc914640efdf96bd4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48423960"
---
# <a name="configuring-the-ftp-adapter"></a>Configurar el adaptador de FTP


## <a name="before-you-begin"></a>Antes de comenzar
- El adaptador de FTP admite la lectura y escritura de datos de un servidor FTP seguro. El adaptador admite la transferencia de archivos desde un servidor FTP mediante Capa de sockets seguros (SSL)/Seguridad de nivel de transporte (TLS). 
- El adaptador de FTP admite la descarga de archivos desde ubicaciones de archivo de solo lectura. 
- El adaptador de FTP admite la transferencia atómica de archivos también para el modo ASCII.

Consulte [procedimientos recomendados y recomendaciones para el adaptador FTP](../core/best-practices-and-recommendations-for-the-ftp-adapter.md).


## <a name="configure-the-receive-location"></a>Configurar la ubicación de recepción

FTP puede establecer las propiedades de adaptador de ubicación de recepción en la consola de administración de BizTalk Server. Si no se establecen propiedades en la ubicación de recepción, se usan los valores predeterminados del controlador de recepción en la consola de administración de BizTalk Server.  

> [!NOTE]
>  Antes de completar el siguiente procedimiento, debe haber agregado un puerto de recepción. Consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
> 1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación en el que desea crear una ubicación de recepción.  

2. En el panel izquierdo, haga clic en el **puertos de recepción** nodo. En el panel derecho, haga clic en el puerto de recepción que está asociado a una ubicación de recepción existente o que desee asociar a una nueva ubicación de recepción y, a continuación, haga clic en **propiedades**.  

3. En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**. En el panel derecho, haga doble clic en una existente, ubicación de recepción o haga clic en **New** para crear una nueva ubicación de recepción.  

4. En el **propiedades de ubicación de recepción** cuadro de diálogo el **transporte** junto a la sección **tipo**, seleccione **FTP** en la lista desplegable y a continuación, haga clic en **configurar**.  

5. En **propiedades de transporte FTP**, realice lo siguiente:  

   **Proceso por lotes**

   |Use|Para|  
   |--------------|----------------|  
   |**Número máximo de archivos**|Especificar el número máximo de archivos por lote de BizTalk Server.<br /><br /> El cero (0) indica que no hay ningún límite.<br /><br /> **Valor predeterminado:** 0|  
   |**Tamaño máximo**|Especificar el número máximo de bytes por lote de BizTalk Server.<br /><br /> El cero (0) indica que no hay ningún límite.<br /><br /> **Valor predeterminado:** 0|  

   **Firewall de**

   |Use|Para|  
   |--------------|----------------|     
   |**Dirección**|Especificar la dirección del servidor de seguridad, ya sea un nombre DNS o una dirección IP.|  
   |**Modo**|Especificar el modo en el que el adaptador establece la conexión con el servidor FTP.<br /><br /> **Los valores válidos:** pasiva y activa<br /><br /> En modo activo, el servidor FTP se conecta a un puerto abierto por el adaptador FTP. En modo pasivo, el adaptador FTP se conecta a un puerto abierto por el servidor FTP. Modo activo puede no funcionar si utiliza una dirección IP interna y se conecta a una dirección IP externa. En este caso, deberá usar el modo pasivo o modo activo con una puerta de enlace de capa de aplicación (ALG) con compatibilidad con FTP.<br /><br /> **Valor predeterminado:** activo|  
   |**Contraseña**|Especificar la contraseña del servidor de seguridad.|  
   |**Puerto**|Especificar el puerto del servidor de seguridad.<br /><br /> **Los valores válidos:** 1 y 65535, ambos inclusive<br /><br /> **Valor predeterminado:** 21|  
   |**Tipo**|Especificar el tipo de servidor de seguridad implementado.<br /><br /> **Los valores válidos:** ninguno, Socks 4 y Socks 5<br /><br /> **Valor predeterminado:** ninguno|  
   |**Usuario**|Especificar el nombre de usuario del servidor de seguridad.|  

   **FTP**


   |         Use         |  Para  |
   |---|---|
   |       **Cuenta**        |  Especificar el nombre de cuenta para el servidor FTP. Esta opción está en desuso y se desaconseja el uso de esta propiedad.  |
   |      **Después de Get**       | Especifique los comandos FTP que ejecutar después del archivo GET. Separe los comandos con un punto y coma (;). |
   |      **Antes de Get**      |   Especifique los comandos FTP que se ejecutarán antes del archivo GET. Separe los comandos con un punto y coma (;). **Nota:** no se admite el comando QUIT antes del archivo GET.   |
   |   **Umbral de error**    |   Especifique el número de errores que puede encontrar el servidor BizTalk Server antes de la ubicación está deshabilitada.<br /><br /> **Valor predeterminado:** 10   |
   |      **Máscara de archivo**       |  Especificar el filtro de máscara de archivo que se utilizará al transmitir los archivos.  |
   |        **Carpeta**        |   Especificar la ubicación de sondeo del servidor FTP.  |
   |   **Tipo de servidor de FTP**    | Nuevo a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. <br/><br/>Utilice esta propiedad para elegir un servidor FTP que no requieren el comando SYST. Las opciones son None, AIX, detectar, GXS, MVS, OS400 y otros. <br/><br/>Si establece en **ninguno**, se usa el comando SYST. **Otros** se usa cuando el tipo de sistema operativo no caben dentro de cualquiera de las categorías especificadas. <br /><br /> **Valor predeterminado:** ninguno |
   |         **Log**          |  Especifique la ubicación para guardar una copia del archivo de registro. Este archivo se utiliza para diagnosticar las condiciones de error que se producen al enviar o recibir archivos mediante FTP.    |
   |    **Tamaño máximo de archivo**     |   Especificar el tamaño máximo de archivos descargables en megabytes (MB).<br /><br /> Cero (0) indica que no hay límite de tamaño de archivo.<br /><br /> **Valor predeterminado:** 100    |
   |       **Contraseña**       |   Especificar la contraseña de usuario para iniciar la sesión en el servidor FTP. |
   |         **Puerto**         |  Especificar la dirección del puerto de este servidor FTP.<br /><br /> **Valor predeterminado:** 21 |
   |    **Representación**    |  Seleccionar el modo en el que el FTP recibe los datos.<br /><br /> **Los valores válidos:** binario o ASCII<br /><br /> **Valor predeterminado:** binario  |
   |        **Server**        |   Especificar el nombre de servidor o la dirección IP del servidor FTP. **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.  |
   |    **Afiliada de SSO**     |  Especificar la aplicación afiliada de inicio de sesión único empresarial.  |
   | **Use la lista de nombres (NLST)** |  Especifique cómo el adaptador muestra una lista de archivos. Para ver los nombres de archivo en lugar de la lista de archivos definidos por el sistema, establezca este valor en Sí.<br /><br /> **Valor predeterminado:** n   |
   |      **Nombre de usuario**       |  Especificar el nombre de usuario para iniciar la sesión en el servidor FTP.  |

   **Sondeo**

   |Use|Para|  
   |--------------|----------------|         
   |**Eliminar después de descargar**|Especifique si el adaptador elimina un archivo del servidor FTP después de descargarlo.<br /><br /> **Valor predeterminado:** Sí **Nota:**|  
   |**Habilitar la comparación de marca de tiempo**|Especifique si el adaptador vuelve a descargar un archivo en función de si la marca de tiempo se ha modificado. En aquellos casos en los que el adaptador no tena permisos de eliminación en el servidor de FTP, el comando MDTM (Hora de modificación) permite al adaptador saber si se ha modificado o no un archivo desde la última descarga.  Según el valor de esta propiedad, el archivo se descarga de nuevo.<br /><br /> **Valor predeterminado:** No **Nota**: en caso de que el servidor FTP no admite MDTM, establezca el **intervalo para volver a descargar** propiedad. **Nota:** esta propiedad solo es aplicable cuando **eliminar después de descargar** está establecida en no.|  
   |**Intervalo**|Especificar el número de intervalo de sondeo de esta ubicación. Para efectuar un sondeo continuo, establezca este valor en cero (0).<br /><br /> **Valor predeterminado:** 60|  
   |**Intervalo para volver a descargar**|Especificar el intervalo después del cual el adaptador descarga archivos de nuevo. Esta propiedad solo es aplicable cuando ambos **eliminar después de descargar** y **habilitar comparación en marca de tiempo** se establecen en no.<br /><br /> **Valor predeterminado:** -1<br /><br /> -1 indica que el adaptador no descargará los archivos de nuevo.<br /><br /> 0 indica que el adaptador descargará el archivo en cada ciclo de sondeo.|  
   |**Unidad**|Especifique el tipo de unidades para el **intervalo** y **intervalo para volver a descargar** propiedades.<br /><br /> **Los valores válidos:** segundos, minutos, horas y días<br /><br /> **Valor predeterminado:** segundos|  

   **SSL**

   |Use|Para|  
   |--------------|----------------|
   |**Hash del certificado de cliente**|Especifique el hash SHA1 del certificado de cliente que se debe usar en la negociación de la Capa de sockets seguros (SSL).<br /><br /> En función de este hash, el certificado de cliente se toma del almacén personal de la cuenta de usuario bajo la que se ejecuta la instancia de host de BizTalk.|  
   |**Modo de conexión FTPS**|Especifique el modo de conexión SSL realizada al servidor FTPS.<br /><br /> **Los valores válidos:** implícita o explícita<br /><br /> **Valor predeterminado:** explícita|  
   |**Usar protección de datos**|Especifique Sí, si el adaptador debe usar el cifrado SSL cuando envía y recibe archivos de datos del servidor FTPS. Especifique No para que el adaptador envíe y reciba archivos de datos como texto sin formato. **Nota:** esta propiedad es aplicable solo si el **usar SSL** propiedad está establecida en Sí. <br /><br /> **Los valores válidos:** Sí o No<br /><br /> **Valor predeterminado:** sí|  
   |**Usar SSL**|Especifique si el adaptador FTP debe usar SSL para comunicarse con el servidor FTPS.<br /><br /> **Los valores válidos:** Sí o No<br /><br /> **Valor predeterminado:** n|  

   **Parámetros de ajuste**


   |         Use         | Para  |
   |---|---|
   | **Tiempo de espera de datos de recepción** | Especifique el tiempo en milisegundos antes de que se anule la llamada de recepción. Esta propiedad se usa para evitar que un servidor lente haga que la ubicación de recepción deje de responder.<br /><br /> **Valor predeterminado:** 90000 |
   |   **Carpeta temporal**   |  Especificar la ubicación de una carpeta temporal. Se usa esta ubicación para garantizar la recuperación tras un error de transferencia.                                                |


6. Haga clic en **Aceptar** para guardar la configuración.  

7. En el **propiedades de ubicación de recepción** diálogo cuadro, escriba los valores adecuados para completar la configuración de la ubicación de recepción y, a continuación, haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de las ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  

> [!NOTE]
>  No configure varias ubicaciones de recepción de FTP para sondear la misma dirección URL de FTP. Si varias ubicaciones de recepción de FTP sondean la misma dirección URL de forma simultánea, cada ubicación de recepción puede recibir una copia del archivo, lo que puede da lugar al duplicado de datos. Este comportamiento tiene lugar porque el protocolo FTP no tiene disposición para bloquear archivos al leerlos desde la dirección URL de destino.  
>   
>  Para proporcionar alta disponibilidad para el FTP del adaptador de recepción, debe configurar el FTP de recepción para su ejecución en una instancia de Host de BizTalk en clúster. Consulte [consideraciones para ejecutar controladores de adaptador en un Host agrupado](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  

## <a name="configure-the-send-port"></a>Configurar el puerto de envío

Puede establecer propiedades de adaptador de puerto de envío FTP en la consola de administración de BizTalk Server. Si no se establecen las propiedades del puerto de envío, el valor predeterminado se usan los valores en la consola de administración de BizTalk Server de controlador de envío.  

1. En la consola de administración de BizTalk Server, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configurar todas las opciones de puerto de envío y en el **transporte** sección de la **General** , especifique **FTP** para el **tipo** opción.  

2. En el **General** página, en el **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  

3. En **propiedades de transporte FTP**, realice lo siguiente:  

   **Firewall de**

   |Use|Para|  
   |--------------|----------------|    
   |**Dirección**|Especificar la dirección del servidor de seguridad, ya sea un nombre DNS o una dirección IP.|  
   |**Modo**|Seleccionar el modo en el que el adaptador establece la conexión con el servidor FTP.<br /><br /> **Los valores válidos:** pasiva y activa<br /><br /> En modo activo, el servidor FTP se conecta a un puerto abierto por el adaptador FTP. En modo pasivo, el adaptador FTP se conecta a un puerto abierto por el servidor FTP. Modo activo puede no funcionar si utiliza una dirección IP interna y se conecta a una dirección IP externa. En este caso, deberá usar el modo pasivo o modo activo con una puerta de enlace de capa de aplicación (ALG) con compatibilidad con FTP.<br /><br /> **Valor predeterminado:** activo|  
   |**Contraseña**|Especificar la contraseña del servidor de seguridad.|  
   |**Puerto**|Especificar el puerto del servidor de seguridad.<br /><br /> **Los valores válidos:** 1 y 65535, ambos inclusive<br /><br /> **Valor predeterminado:** 21|  
   |**Tipo**|Seleccionar el tipo de servidor de seguridad implementado.<br /><br /> **Los valores válidos:** Socks 4, Socks 5, ninguno<br /><br /> **Valor predeterminado:** ninguno|  
   |**Usuario**|Especificar el nombre de usuario del servidor de seguridad.|  

   **FTP**


   |       Use       | Para |
   |---|---|
   |     **Cuenta**      |  Opcional. Especificar el nombre de cuenta para el servidor FTP. Esta opción se ha dejado de usar y se desaconseja el uso de esta propiedad. |
   |    **Después de Put**     |  Especificar los comandos FTP que se ejecutarán después del archivo PUT. Separe los comandos con un punto y coma (;).  |
   | **Asignar almacenamiento** |  Especificar si se asigna espacio de almacenamiento para sistemas de hosts heredados. Esta opción se proporciona para la compatibilidad con versiones anteriores.<br /><br /> **Los valores válidos:** No y Sí<br /><br /> **Valor predeterminado:** n  |
   |    **Antes de colocar**    |  Especificar los comandos FTP que se ejecutarán antes del archivo PUT; por ejemplo, comandos para cambiar los valores predeterminados en el servidor FTP. Separe los comandos con un punto y coma (;). No se requiere ningún comando open. **Nota:** no se admite el comando QUIT antes del archivo PUT.  |
   |      **Carpeta**      |  Especificar la ubicación a la que se moverán los archivos del servidor FTP. |
   | **Tipo de servidor de FTP**  | Nuevo a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]. <br/><br/>Utilice esta propiedad para elegir un servidor FTP que no requieren el comando SYST. Las opciones son None, AIX, detectar, GXS, MVS, OS400 y otros. <br/><br/>Si establece en **ninguno**, se usa el comando SYST. **Otros** se usa cuando el tipo de sistema operativo no caben dentro de cualquiera de las categorías especificadas. <br /><br /> **Valor predeterminado:** ninguno |
   |       **Log**        |  Especificar la ubicación para guardar una copia del archivo de registro. Use este archivo para diagnosticar las condiciones de error que se producen al enviar o recibir archivos a través del adaptador de FTP.    |
   |     **Contraseña**     |  Especifique la contraseña para iniciar sesión en el servidor de FTP. |
   |       **Puerto**       | Especifique la dirección del puerto para el servidor FTP.<br /><br /> **Valor predeterminado:** 21  |
   |  **Representación**  | Seleccione cómo envía los datos el adaptador de FTP, como binarios o como ASCII.<br /><br /> **Los valores válidos:** binario o ASCII<br /><br /> **Valor predeterminado:** binario   |
   |      **Server**      |  Especificar el nombre de servidor o la dirección IP del servidor FTP.  |
   |  **Afiliada de SSO**   |  Especificar la aplicación afiliada de inicio de sesión único empresarial. |
   | **Nombre de archivo de destino** |  Especificar un nombre alternativo para el archivo. Conservar el nombre predeterminado garantiza que los nombres de mensaje únicos para cada mensaje enviado.<br /><br /> **Valor predeterminado:** %MessageID%.xml  |
   |    **Nombre de usuario**     |  Especificar el nombre de usuario para iniciar la sesión en el servidor FTP. |

   **SSL**

   |Use|Para|  
   |--------------|----------------|
   |**Hash del certificado de cliente**|Especifique el hash SHA1 del certificado de cliente que se debe usar en la negociación de la Capa de sockets seguros (SSL).<br /><br /> En función de este hash, el certificado de cliente se toma del almacén personal de la cuenta de usuario bajo la que se ejecuta la instancia de host de BizTalk.|  
   |**Modo de conexión FTPS**|Especifique el modo de conexión SSL realizada al servidor FTPS.<br /><br /> **Los valores válidos:** implícitos o explícitos<br /><br /> **Valor predeterminado:** Explicit|  
   |**Usar protección de datos**|Especifique Sí, si el adaptador debe usar el cifrado SSL cuando envía y recibe archivos de datos del servidor FTPS. Especifique No para que el adaptador envíe y reciba archivos de datos como texto sin formato. **Nota:** esta propiedad es aplicable solo si el **usar SSL** propiedad está establecida en Sí. <br /><br /> **Los valores válidos:** Sí o No<br /><br /> **Valor predeterminado:** sí|  
   |**Usar SSL**|Especifique si el adaptador FTP debe usar SSL para comunicarse con el servidor FTPS.<br /><br /> **Los valores válidos:** Sí o No<br /><br /> **Valor predeterminado:** n|  

   **Parámetros de ajuste**


   |       Use       | Para  |
   |---|---|
   | **Límite de conexiones** | Especificar el número máximo de conexiones FTP simultáneas que se pueden abrir con el servidor. El valor 0 significa que no hay ningún límite.<br /><br /> **Valor predeterminado:** 0 **Nota:** esta propiedad reemplaza la entrada del registro que se utilizó en versiones anteriores de BizTalk Server para regir el límite de conexiones. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] omite la entrada del registro que se usan para controlar el límite de conexiones. |
   | **Carpeta temporal** |      Especificar la ubicación para una carpeta temporal del servidor FTP. El archivo se carga primero aquí y, a continuación, se mueven a la carpeta de FTP de destino. En caso de error de transferencia, el adaptador reinicia la carga de archivos en modo ASCII de transferencia y reanuda en modo binario de transferencia. **Nota:** si la transferencia de archivos es atómica entre la ubicación temporal y la ubicación correspondiente en el servidor FTP, la carga de archivos también será atómica.      |

4. Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.   


## <a name="ftp-commands-required-by-the-ftp-adapter"></a>Comandos FTP que requiere el adaptador de FTP  
El adaptador de FTP está sujeto a las limitaciones del protocolo FTP y requiere que determinados comandos FTP estén disponibles en el servidor FTP de origen o de destino.  

El adaptador de FTP funciona como un cliente FTP y puede requerir que los siguientes comandos estén disponibles en el servidor FTP para funcionar correctamente: 


| Comando  |  Requiere de recepción  |  Requerido por el envío  |
|---|---|---|
|   SYST   | ✔ <br/><br/>Opcional a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] | ✔<br/><br/>Opcional a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] |
|  ALMACÉN   |  |  ✔  |
|   RETR   |  ✔  |  |
|   User   |  ✔  |  ✔  |
|   PASS   |  ✔  |  ✔  |
|   CWD    |  ✔  |  ✔  |
|   QUIT   |  ✔  |  ✔  |
|   PORT   |  ✔  |  ✔  |
|   PASV   |  ✔  |  ✔  |
|   ABOR   |  ✔  |  ✔  |
|   TYPE   |  ✔  |  ✔  |
|   RNFR   |  ✔  |  ✔  |
|   RNTO   |  ✔  |  ✔  |
|   DELE   |  ✔  |  ✔  |
|   PWD    |  ✔  |  ✔  |
|   LIST   |  ✔  |  ✔  |
|   NLST   |  ✔  |  ✔  |
|   NOOP   |  ✔  |  ✔  |
|   APPE   |  |  ✔   |
|   ALLO   |  ✔  |  ✔  |
|   MDTM   |  ✔  |  |
| AUTH TLS |  ✔  |  ✔  |
|   PBSZ   |  ✔  |  ✔  |
|   PROT   |  ✔  |  ✔  |

 Para obtener más información acerca de estos comandos FTP, consulte:  

-   [Protocolo de transferencia de RFC 959 - archivo](http://go.microsoft.com/fwlink/p/?LinkId=119603) ( http://go.microsoft.com/fwlink/p/?LinkId=119603) )  

-   [RFC 4217 - protección FTP con TLS](http://go.microsoft.com/fwlink/p/?LinkId=183154) ( http://go.microsoft.com/fwlink/p/?LinkId=183154) )  

-   [RFC 3659 - extensiones FTP](http://go.microsoft.com/fwlink/p/?LinkId=183155) ( http://go.microsoft.com/fwlink/p/?LinkId=183155) )  

## <a name="configuring-an-ftp-adapter-to-work-with-legacy-hosts"></a>Configuración de adaptador de FTP para trabajar con Hosts heredados

Esta sección se aborda en lo que necesita saber para facilitar la comunicación entre el adaptador de FTP y un equipo (mainframe).   
> [!NOTE]
>  No se puede usar la función de carpeta temporal al enviar archivos a un host AS400 o MVS. La entrada en este campo no se admite y producirá errores.  

> [!IMPORTANT]
>  La siguiente información se proporciona como guía y no se debería sustituir por la información que se encuentra en la documentación de IBM o AS400.  

## <a name="mvs"></a>MVS  
 Para enviar archivos a un servidor FTP de un gran sistema (mainframe), éste debe admitir los grupos de datos de generaciones de IBM (GDG, del inglés Generation Data Group). En el campo de nombre, cada nombre de archivo anexará un (+1) al nombre de archivo de destino (una ruta completa entre comillas).  

## <a name="as400"></a>AS400  
 Existen tres métodos para dar nombre a los archivos y definir sus rutas cuando se transfieren archivos a un sistema AS400 y desde él:  

-   **Campo de nombre de archivo**: cuando se envía un archivo a un servidor FTP, escriba el nombre de archivo en el **Filename** campo. El nombre de archivo debe cumplir las convenciones de asignación de nombre de archivo del sistema AS400, pues el archivo se almacenará en el sistema de archivos de biblioteca.  

-   **Comando quote**: Use el comando Quote para ejecutar un script en el equipo remoto. Escriba el comando Quote en el **antes de obtener**, **antes de colocar**, **después de obtener**, y **después de PUT** campos en cualquiera de los puntos de conexión. Escriba el comando de comillas en el formato siguiente:  

    ```  
    QUOTE RCMD <command to be run on the remote system>.  
    ```  

-   **Integrado del sistema de archivos (IFS)**: IFS es un área en el sistema AS400 que permite el almacenamiento de archivos basados en PC y, por lo tanto, las mismas convenciones de nomenclatura que un PC. Para usar IFS en lugar del sistema de archivos de biblioteca predeterminado, el primer comando que tiene que introducir es `quote site namefmt 1`. Este comando le indica al sistema AS400 que tiene que utilizar las convenciones de asignación de nombres de IFS.    


## <a name="more-good-stuff"></a>Otros recursos útiles

[Propiedades y esquema de propiedades del adaptador de FTP](../core/ftp-adapter-property-schema-and-properties.md)  

[Los procedimientos recomendados y recomendaciones para el adaptador FTP](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[Adaptador de FTP](../core/ftp-adapter.md)

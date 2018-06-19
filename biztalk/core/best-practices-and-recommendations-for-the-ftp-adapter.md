---
title: Prácticas recomendadas y recomendaciones para el adaptador de FTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, FTP adapters
- FTP adapters, best practices
ms.assetid: f73b2016-d48c-48d8-9ba0-96e26b694d1e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85967756089be91939bf5b6f73b12d36ed8caa51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234492"
---
# <a name="best-practices-and-recommendations-for-the-ftp-adapter"></a>Prácticas recomendadas y recomendaciones para el adaptador de FTP
Obtenga información acerca de las prácticas recomendadas, las recomendaciones de seguridad y las mejoras del adaptador de FTP.

## <a name="best-practices"></a>Procedimientos recomendados  
  
-   Elimine de la carpeta temporal, con cierta regularidad, los archivos parcialmente recibidos. De este modo evitará que consuman recursos del equipo o que ocasionen interrupciones en el servicio.  
  
-   Cuando utilice un servidor de transmisión por secuencias, deniegue el acceso de lectura al nuevo archivo hasta que la base de datos de cuadro de mensajes haya recibido la totalidad del archivo. Si el adaptador de FTP envía un archivo parcial a la base de datos de cuadro de mensajes, la base de datos almacenará el mensaje correctamente, pero el adaptador de FTP no podrá eliminar el mensaje parcial de la ubicación de recepción.  
  
-   Para garantizar un alto grado de disponibilidad del controlador de recepción del adaptador de FTP, dicho controlador deberá configurarse de modo que se ejecute en una instancia de host de BizTalk agrupada. Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).  

## <a name="security-recommendations-and-tips"></a>Sugerencias y recomendaciones de seguridad

BizTalk Server puede recibir archivos desde un servidor de protocolo de transferencia de archivos (FTP) y enviar archivos a un servidor FTP para otras aplicaciones. BizTalk Server no actúa como servidor FTP.  
  
 FTP es, por naturaleza, no seguro: el nombre de usuario, contraseña y otras credenciales atraviesan la red en texto no cifrado. Del mismo modo, los archivos que se cargan o descargan lo hacen también en texto sin cifrar, por lo que su contenido puede ser visto y utilizado de forma malintencionada. Además, un atacante podría suplantar el propio servidor FTP, lo que se conoce como un ataque de servidor roque. En este caso, no se puede saber si un servidor FTP concreto es realmente el equipo con el que intenta comunicarse.  
  
 Para solucionar estos problemas, el adaptador de FTP admite el protocolo SSL/TLS que garantiza la confidencialidad de datos mediante cifrado.  
  
 Para las consideraciones de seguridad general cuando se usa el protocolo FTP, consulte el [preguntas frecuentes](http://go.microsoft.com/fwlink/p/?LinkId=24779) (http://go.microsoft.com/fwlink/p/?LinkId=24779).   
  
 Se recomienda que utilice las siguientes directrices para proteger e implementar el adaptador de FTP en su entorno:  

- Proteger el servidor y limite el acceso a los datos. Dado que el protocolo FTP no es un protocolo seguro, siempre será vulnerable. Puede asegurarse de que el servidor FTP es seguro mediante una conexión dedicada y limitando el servidor y la conexión entre el servidor BizTalk Server y el host FTP. También se pueden configurar las directrices de seguridad del servidor FTP para permitir conexiones seguras con el cliente de FTP.  

- Configure el adaptador de FTP para usar el protocolo Capa de sockets seguros (SSL) para la comunicación entre el adaptador y el servidor FTP. El protocolo SSL asegura la confidencialidad de datos mediante cifrado. Esto significa que los identificadores de usuario y contraseñas se cifran y no se envían como texto sin formato. Con el adaptador de FTP, también puede cifrar el canal de datos de la conexión FTP. Vea **mejoras** (en este tema).
  
-   Para lograr una transferencia segura de archivos, configure las propiedades específicas de SSL proporcionadas por el adaptador FTP. Vea **mejoras** (en este tema). 
  
-   El adaptador de FTP admite la solicitud de FTP de comentarios (RFC 959). Consulte la [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?LinkId=24781) (http://go.microsoft.com/fwlink/p/?LinkId=24781). El adaptador de FTP no admite el protocolo de FTP seguro (SFTP). Consulte la [adaptador SFTP](../core/sftp-adapter.md).
  
-   Puede utilizar el adaptador de FTP en servidores de seguridad. Dependiendo del tipo de firewall usado, tendrá que configurar una o varias de las siguientes propiedades de firewall: nombre de usuario, contraseña, equipo, puerto, tipo de servidor de seguridad (ninguno, socks 4, socks 5) y el modo.  
  
-   Se recomienda que colocar el servidor FTP remoto en una ubicación segura. Debe garantizar la seguridad física y de red de este servidor para minimizar los ataques de servidores Rogue.  
  
-   El adaptador de FTP admite el uso de inicio de sesión único (SSO) empresarial. Vea [implementar Enterprise Single Sign-On](../core/implementing-enterprise-single-sign-on.md).  
  
-   De forma predeterminada, el adaptador de recepción FTP debe tener permisos de escritura en el servidor FTP porque el adaptador elimina el archivo del servidor después de la descarga. Sin embargo, el adaptador de FTP admite la descarga de archivos desde ubicaciones de solo lectura. Vea **mejoras** (en este tema).
  
- Cuando se utilice un puerto de envío FTP, se debe especificar y almacenar una combinación de contraseña e Id. al configurar el puerto de envío. El adaptador utiliza esta información para conectarse al servidor FTP. Las credenciales de usuario se almacenan en una base de datos de SQL Server como texto sin formato. En un puerto de envío dinámico, las credenciales se envían al servidor FTP. Si los requisitos del entorno de producción garantizan una mayor seguridad, utilice credenciales anónimas para el servidor.  
  
-   Cuando el sistema le pide que especifique una cuenta, le recomendamos que escriba una cuenta de usuario existente y no la cuenta de sistema local. Esto hace posible implementar una mayor seguridad y permite la ejecución del adaptador en modo desatendido, sin iniciar sesión.  

## <a name="enhancements"></a>Mejoras

### <a name="transferring-data-to-and-from-a-secure-ftp-server"></a>Transferir datos hacia y desde un servidor FTP seguro  
 El adaptador de FTP admite las transferencias de archivos desde un servidor FTPS mediante capa de Sockets seguros (SSL) o seguridad de nivel de transporte (TLS). SSL/TLS garantiza la confidencialidad de los datos mediante el cifrado. Debe habilitar el modo seguro mediante la configuración de propiedades específicas de SSL proporcionadas por el adaptador. Puesto que el adaptador permite tanto la lectura como la escritura de datos del servidor FTP, las propiedades específicas de SSL están disponibles al configurar controladores y puertos de envío, además de con los controladores y ubicaciones de recepción.  

A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], el adaptador de FTP ya no requiere que el comando SYST: 

- **Tipo de servidor FTP** property: establezca esta propiedad para utilizar un servidor que no requiere el comando SYST.
   
 Están disponibles las opciones siguientes para configurar las propiedades específicas de SSL:  

-   **Usar SSL** property: establezca esta propiedad para que el adaptador FTP debe usar SSL para cada sesión de transferencia.  
  
-   **Habilitar la protección de datos** property: establezca esta propiedad para activar el cifrado de datos. Las directivas de seguridad del servidor FTPS deben permitir conexiones SSL seguras con el adaptador para que esta configuración funcione.  
  
-   **Modo de conexión FTPS** property: establezca esta propiedad para determinar cuándo se activa la seguridad:  
  
    -   En **implícitas** , modo de seguridad se activa automáticamente en cuanto el adaptador se conecta al servidor.  
  
    -   En **Explicit** modo, el adaptador envía un comando para iniciar un canal de control seguro.  
  
> [!NOTE]
>  El adaptador FTP no admite la comprobación de revocaciones en los certificados del servidor.  
  
### <a name="support-for-downloading-files-from-locations-marked-as-read-only"></a>Compatibilidad para la descarga de archivos de ubicaciones marcadas como de solo lectura  
El adaptador de FTP admite la descarga de archivos desde ubicaciones de archivo de solo lectura. El adaptador mantiene ahora una lista de archivos descargados en una base de datos. En la siguiente descarga, la lista de archivos del servidor FTP se compara con la lista de archivos mantenidos por el adaptador y, únicamente se descargan los nuevos archivos en el servidor. Para admitir escenarios donde se actualiza un archivo existente entre dos descargas, puede configurar el adaptador para comprobar las marcas de tiempo del archivo estableciendo el **habilitar comparación en marca de tiempo** ubicación de recepción de propiedad para el FTP. En tales casos, incluso si el nombre de archivo es el mismo pero se actualiza la marca de tiempo, el adaptador descarga el archivo.  
  
 Algunas veces el servidor FTP no admite la asociación de una marca de tiempo modificada con un archivo. En estos casos, el adaptador permite especificar un intervalo después del cual el archivo se volverá a descargar. Este intervalo se configura estableciendo la **volver a descargar intervalo** ubicación de recepción de propiedad para el FTP.  
  
 En la tabla siguiente enumera el comportamiento esperado del adaptador de FTP para diferentes valores establecidos para la **eliminar después de descargar**, **habilitar comparación en marca de tiempo** y **a descargar intervalo** propiedades.  
  
|Eliminar después de la descarga|Habilitar la comparación en marca de tiempo|Intervalo para volver a descargar|Comportamiento del adaptador|  
|---|---|---|---|  
|Sí|No aplicable|No aplicable|El adaptador elimina un archivo del servidor FTP después de descargarlo. Éste es el comportamiento predeterminado del adaptador.|  
|No|Sí|No aplicable|El adaptador no elimina un archivo del servidor FTP después de descargarlo. En su lugar, el adaptador compara la marca de tiempo de la última modificación del archivo mediante el comando MDTM. Según la marca de tiempo, el adaptador descarga el archivo de nuevo.|  
|No|No|Aplicable|El adaptador de FTP descarga un archivo del servidor FTP después del intervalo que especifique, independientemente de si el archivo se ha modificado o no.|  
  
### <a name="support-for-atomic-file-transfer-in-ascii-mode"></a>Compatibilidad para la transferencia de archivos atómica en modo ASCII  
 El adaptador de FTP admite la transferencia de archivos atómica para el modo ASCII. Para habilitar la transferencia de archivos atómica para el modo ASCII, el adaptador utiliza la **carpeta temporal** propiedad. Esta propiedad define una ubicación temporal en el servidor FTP a la que se mueve el archivo en primer lugar. Después de que se haya transferido completamente el archivo a la ubicación temporal, se mueve a la ubicación pertinente del servidor FTP. Aquí, se supone que la transferencia de archivos es atómica entre la ubicación temporal y la ubicación correspondiente del servidor FTP.  
  
> [!NOTE]
>  La extensión de usar la carpeta temporal al archivo ASCII solo es aplicable la **enviar**y no se aplica a **recepción**. El motivo principal para implementar esta característica es que una aplicación de terceros no lee un archivo hasta que está totalmente escrito. Si BizTalk recibe el archivo, el adaptador enviará el archivo a BizTalk solo después de leerlo completamente.  
  
> [!NOTE]
>  En modo binario, el **carpeta temporal** propiedad también puede utilizarse para reanudar la transferencia de archivos si se produce un error en medio. No se aplica al modo ASCII. Para el modo ASCII, el **carpeta temporal** propiedad solo se utiliza para la transferencia de archivos atómica.  
  
 
## <a name="next"></a>Siguiente 
[Configurar el adaptador FTP](../core/configuring-the-ftp-adapter.md)  

## <a name="see-also"></a>Vea también  
 [Puertos para los servidores de envío y recepción](../core/ports-for-the-receive-and-send-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)

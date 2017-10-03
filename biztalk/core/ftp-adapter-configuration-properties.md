---
title: "Propiedades de configuración del adaptador FTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- FTP adapters, properties
- FTP adapters, code sample
- FTP adapters, send ports
- FTP adapters, receive locations
- send ports, adapters
ms.assetid: 88a2084e-cb26-4136-9077-8b9463062ccc
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2c7895d8f5fc3789a02c72743705a4a03a9f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ftp-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de FTP
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de FTP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|Especificar la ruta de acceso completa a la ubicación supervisada por la ubicación de recepción.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|serverAddress|VT_BSTR|Especificar el nombre de servidor o la dirección IP del servidor FTP.|Ninguno|Ninguno|  
|serverPort|VT_BSTR|Especificar el puerto TCP mediante el que se establecerá la comunicación con el servidor FTP de destino.|Ninguno|Ninguno|  
|userName|VT_BSTR|Especifique el nombre de usuario que se usa para tener acceso al servidor FTP.|Ninguno|Ninguno|  
|password|VT_BSTR|Especificar la contraseña que se usa para obtener acceso al servidor FTP.|Siempre se marca este valor cuando se exporta un archivo de enlace. Esta propiedad se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
|fileMask|VT_BSTR|Especificar el filtro de máscara de archivo que se utilizará al transmitir los archivos.|Ninguno|Ninguno|  
|targetFolder|VT_BSTR|Especificar la ubicación de sondeo del servidor FTP.|Ninguno|Ninguno|  
|commandLogFilename|VT_BSTR|Especifique la ubicación para guardar una copia del archivo de registro.|Ninguno|Este archivo se utiliza para diagnosticar las condiciones de error que se producen al enviar o recibir archivos mediante el adaptador FTP.|  
|representationType|VT_BSTR|Seleccionar el modo en el que el adaptador FTP recibe los datos.|Los valores válidos son:<br /><br /> -Binario<br />-ASCII|El valor predeterminado es binario.|  
|spoolingFolder|VT_BSTR|Especificar la ubicación para una carpeta temporal del servidor FTP. Esta carpeta se utiliza para garantizar la recuperación tras un error de transferencia.|Ninguno|Ninguno|  
|receiveDataTimeOut|VT_BSTR|Especifique el tiempo en milisegundos antes de que se anule la llamada de recepción. Se utiliza para evitar que un servidor lento haga que la ubicación de recepción se bloquee.|Ninguno|El valor predeterminado es 90000.|  
|maximumBatchSize|VT_BSTR|Especificar el número máximo de bytes por lote de BizTalk Server.|Ninguno|Ninguno|  
|maximumNumberOfFiles|VT_BSTR|Especificar el número máximo de archivos por lote de BizTalk Server.|Ninguno|Ninguno|  
|passiveMode|VT_BSTR|Especificar el modo en el que el adaptador establece la conexión con el servidor FTP.|Los valores válidos son:<br /><br /> -Pasivo<br />-Active|El valor predeterminado es Activo.|  
|useNLST|VT_BSTR|Especificar como Sí para recuperar únicamente los nombres de archivo en lugar de listado de archivos definido por el sistema predeterminado.|Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es no.|  
|beforeGet|VT_BSTR|Especificar los comandos FTP que se ejecutarán antes del archivo GET.|Separe los comandos con un punto y coma (;) **Nota:** no se admite el comando QUIT antes del archivo GET.|Ninguno|  
|afterGet|VT_BSTR|Especificar los comandos FTP que se ejecutarán después del archivo GET.|Separe los comandos con un punto y coma (;)|Ninguno|  
|firewallType|VT_BSTR|Especificar el tipo de servidor de seguridad implementado.|Los valores válidos son:<br /><br /> -Ninguno<br />-Socks 4<br />-Socks 5|El valor predeterminado es None.|  
|firewallAddress|VT_BSTR|Especificar la dirección del firewall (nombre DNS o dirección IP).|Ninguno|Ninguno|  
|firewallPort|VT_BSTR|Especificar el puerto del servidor de seguridad.|Los valores válidos son de 1 a 65535.|El valor predeterminado es 21.|  
|firewallUserName|VT_BSTR|Especificar el nombre de usuario del servidor de seguridad.|Ninguno|Ninguno|  
|firewallPassword|VT_BSTR|Especificar la contraseña del servidor de seguridad.|Ninguno|Ninguno|  
|pollingUnitOfMeasure|VT_BSTR|Especificar el tipo de unidades de la propiedad pollingInterval.|Los valores válidos son:<br /><br /> -Segundos<br />-Minutos<br />-Horas<br />-Días|El valor predeterminado es Segundos.|  
|pollingInterval|VT_BSTR|Especificar el valor de intervalo de sondeo de esta ubicación.|Ninguno|Para efectuar un sondeo continuo, establezca este valor a 0.<br /><br /> El valor predeterminado es 60.|  
|redownloadInterval|VT_BSTR|Especificar el intervalo en segundos después del cual el adaptador FTP descargará el archivo de nuevo.|Esta propiedad solo es aplicable si se establecen propiedades deleteAfterDownload y enableTimeComparison en no.|El valor -1 indica que el adaptador no descargará nuevamente el archivo.<br /><br /> El valor predeterminado es -1.|  
|ssoAffiliateApplication|VT_BSTR|Especifique la aplicación afiliada de inicio de sesión único (SSO).|Ninguno|Ninguno|  
|errorThreshold|VT_BSTR|Especifique el número de errores que puede encontrar el servidor BizTalk Server antes de que la ubicación está deshabilitada.|Ninguno|El valor predeterminado es 10.|  
|maxFileSize|VT_BSTR|Especificar el tamaño máximo de archivos descargables en megabytes (MB).|Ninguno|Un valor de 0 indica que no hay límite de tamaño de archivo.<br /><br /> El valor predeterminado es 100.|  
|useSsl|VT_BSTR|Especifique este valor en Sí en caso de que el adaptador deba usar SSL al comunicarse con el servidor FTPS.|Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es no.|  
|useDataProtection|VT_BSTR|Especifique este valor en Sí en caso de que el adaptador deba usar el cifrado SSL al enviar y recibir archivos a y del servidor FTPS.|La propiedad es válida si la propiedad useSsl se establece en Sí.<br /><br /> Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es "Sí".|  
|ftpsConnMode|VT_BSTR|Especifique el modo de conexión SSL realizada al servidor FTPS.|Los valores válidos son:<br /><br /> -Explícita<br />-Implícita|El valor predeterminado es Explícito.|  
|clientCertificateHash|VT_BSTR|Especifique el hash SHA1 del certificado del cliente que debe usarse en la negociación de SSL.|Ninguno|En función de este hash, el certificado de cliente se toma del almacén personal de la cuenta de usuario bajo la que se ejecuta la instancia de host de BizTalk.|  
|deleteAfterDownload|VT_BSTR|Especificar como Sí si el adaptador debe eliminar el archivo del servidor FTP después de que finalice la descarga.|Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es "Sí".|  
|enableTimeComparison|VT_BSTR|Especificar como Sí si el adaptador debe volver a descargar el archivo cuando se produzca un cambio en la marca de tiempo del archivo.|Esta propiedad únicamente es válida cuando deleteAfterDownload se establece en No.<br /><br /> El servidor FTP de destino debe admitir el comando MDTM para esta característica.<br /><br /> Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es no.|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>ftp://localhost:21/in/*.xml</uri><serverAddress>localhost</serverAddress><serverPort>21</serverPort><userName>domain\testuser</userName><password>******</password><fileMask>*.xml</fileMask><targetFolder>in</targetFolder><commandLogFilename>c:\temp\realftplog.txt</commandLogFilename><representationType>binary</representationType><maximumBatchSize>0</maximumBatchSize><maximumNumberOfFiles>0</maximumNumberOfFiles><passiveMode>False</passiveMode><firewallType>NoFirewall</firewallType><firewallPort>21</firewallPort><pollingUnitOfMeasure>Seconds</pollingUnitOfMeasure><pollingInterval>5</pollingInterval><errorThreshold>10</errorThreshold><maxFileSize>5000</maxFileSize><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><deleteAfterDownload>True</deleteAfterDownload><enableTimeComparison>False</enableTimeComparison></Config></AdapterConfig></CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de FTP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|Especificar la ruta completa de la ubicación a la que enviar datos.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|serverAddress|VT_BSTR|Especificar la dirección del servidor de seguridad, ya sea un nombre DNS o una dirección IP.|Ninguno|Ninguno|  
|serverPort|VT_BSTR|Especifique la dirección del puerto para el servidor FTP.|Ninguno|El valor predeterminado es 21.|  
|userName|VT_BSTR|Especificar el nombre de usuario para iniciar la sesión en el servidor FTP.|Ninguno|Ninguno|  
|password|VT_BSTR|Especifique la contraseña para iniciar sesión en el servidor de FTP.|Siempre se marca este valor cuando se exporta un archivo de enlace. Esta propiedad se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
|accountName|VT_BSTR|Especificar el nombre de cuenta para el servidor FTP.|Opcional|Ninguno|  
|targetFolder|VT_BSTR|Especificar la ubicación a la que se moverán los archivos del servidor FTP.|Ninguno|Ninguno|  
|targetFileName|VT_BSTR|Especificar un nombre alternativo para el archivo. Al conservar el nombre predeterminado, se garantizan nombres de mensaje únicos para cada mensaje enviado.|Ninguno|El valor predeterminado es %MessageID%.xml.|  
|commandLogFilename|VT_BSTR|Especifique la ubicación para guardar una copia del archivo de registro. Utilice este archivo para diagnosticar las condiciones de error que se producen al enviar o recibir archivos a través del servidor FTP.|Ninguno|Ninguno|  
|representationType|VT_BSTR|Seleccione el modo en que FTP envía los datos, en binario o ASCII.|Los valores válidos son:<br /><br /> -binario<br />-ASCII|El valor predeterminado es Binario.|  
|beforePut|VT_BSTR|Especificar los comandos FTP que se ejecutarán antes del archivo PUT; por ejemplo, comandos para cambiar los valores predeterminados en el servidor FTP.|Separe los comandos con un punto y coma (;). **Nota:** no se admite el comando QUIT antes del archivo PUT.|No se requiere ningún comando open.|  
|afterPut|VT_BSTR|Especificar los comandos FTP que se ejecutarán después del archivo PUT.|Separe los comandos con un punto y coma (;).|Ninguno|  
|allocateStorage|VT_BSTR|Especificar si se asigna espacio de almacenamiento para sistemas de hosts heredados.|Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es no.|  
|spoolingFolder|VT_BSTR|Especificar la ubicación para una carpeta temporal del servidor FTP. Se usa para garantizar la recuperación de un error en la transferencia si el modo de transferencia es binario. Si el modo de transferencia es ASCII, el adaptador reinicia la carga.|Ninguno|Ninguno|  
|connectionLimit|VT_BSTR|Especificar el número máximo de conexiones FTP simultáneas que se pueden abrir con el servidor.|Ninguno|El valor 0 significa que no hay ningún límite.|  
|passiveMode|VT_BSTR|Especificar si se usa el modo pasivo o modo activo.|Los valores válidos son:<br /><br /> -True (modo pasivo)<br />-False (modo activo)|El valor predeterminado es False (modo activo).|  
|firewallType|VT_BSTR|Seleccionar el tipo de servidor de seguridad implementado.|Los valores válidos son:<br /><br /> -Socks 4<br />-Socks 5<br />-Ninguno|El valor predeterminado es None.|  
|firewallAddress|VT_BSTR|Especificar la dirección del servidor de seguridad, ya sea un nombre DNS o una dirección IP.|Ninguno|Ninguno|  
|firewallPort|VT_BSTR|Especificar el puerto del servidor de seguridad.|Los valores válidos son de 1 a 65535.|El valor predeterminado es 21.|  
|firewallUserName|VT_BSTR|Especificar el nombre de usuario del servidor de seguridad.|Ninguno|Ninguno|  
|firewallPassword|VT_BSTR|Especificar la contraseña del servidor de seguridad.|Siempre se marca este valor cuando se exporta un archivo de enlace. Esta propiedad se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
|ssoAffiliateApplication|VT_BSTR|Especifique la aplicación afiliada de inicio de sesión único (SSO).|Ninguno|Ninguno|  
|useSsl|VT_BSTR|Especifique este valor en Sí en caso de que el adaptador deba usar SSL al comunicarse con el servidor FTPS.|Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es no.|  
|useDataProtection|VT_BSTR|Especifique este valor en Sí en caso de que el adaptador deba usar el cifrado SSL al enviar y recibir archivos a y del servidor FTPS.|Esta propiedad es válida si useSsL se establece en Sí.<br /><br /> Los valores válidos son:<br /><br /> -Sí<br />-N|El valor predeterminado es "Sí".|  
|ftpsConnMode|VT_BSTR|Especifique el modo de conexión SSL realizada al servidor FTPS.|Los valores válidos son:<br /><br /> -Explícita<br />-Implícita|El valor predeterminado es Explícito.|  
|clientCertificateHash|VT_BSTR|Especifique el hash SHA1 del certificado de cliente que se debe utilizar en la negociación de SSL.|Ninguno|En función de este hash, el certificado de cliente se toma del almacén personal de la cuenta de usuario bajo la que se ejecuta la instancia de host de BizTalk.|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><serverAddress>TestServer</serverAddress><serverPort>21</serverPort><userName>testuser</userName><password>******</password><accountName>testuser</accountName><targetFolder>output</targetFolder><targetFileName>%MessageID%.xml</targetFileName><commandLogFilename>c:\logfile\ftpsendlog.txt</commandLogFilename><representationType>binary</representationType><beforePut>CDW dir</beforePut><afterPut>CDUP </afterPut><allocateStorage>False</allocateStorage><spoolingFolder>tempfolder</spoolingFolder><connectionLimit>0</connectionLimit><passiveMode>False</passiveMode><firewallType>Socks4</firewallType><firewallAddress>TestServer</firewallAddress><firewallPort>21</firewallPort><firewallUserName>domain\testuser</firewallUserName><firewallPassword>******</firewallPassword><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><uri>ftp://TestServer:21/output/%MessageID%.xml</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  Al especificar los datos de configuración de TransportTypeData para un adaptador creado mediante el marco de trabajo, todos los pares de nombre/valor que se usan deben almacenarse en el \<AdapterConfig > elemento. Puesto que la \<AdapterConfig > elemento especifica la VT_BSTR (vt = "8"), a continuación, el tipo de datos de la \< > caracteres en los datos deben convertirse.
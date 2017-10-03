---
title: "Propiedades de configuración de adaptador de archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- File adapters, code sample
- receive locations, adapters
- File adapters, send ports
- File adapters, receive locations
- File adapters, properties
- send ports, adapters
ms.assetid: 53f4fd17-95b9-4861-b433-772b619e90c7
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c027d5ab993c2110dbcbd6d992859d0d1d4ac7d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de archivo
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de archivo:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|RemoveReceivedFileRetryCount|VT_UI4|Especificar el número de veces que el adaptador de archivo intentará eliminar un archivo que ha leído y enviado a BizTalk Server.|Los valores válidos son de 0 a 100.|El valor predeterminado es 5.|  
|RemoveReceivedFileMaxInterval|VT_UI4|Especificar el intervalo inicial en milisegundos que esperará el adaptador de archivo antes de intentar eliminar un archivo que ha leído y enviado a BizTalk Server.|Los valores válidos son de 1 a 1000.|El valor predeterminado es 10.|  
|FileMask|VT_BSTR|Especificar la máscara de los archivos.|Ninguno|El valor predeterminado es *.xml.|  
|BatchSizeInBytes|VT_UI4|Especifica el total máximo de bytes de un lote de archivos enviado al cuadro de mensajes de BizTalk.|Los valores válidos son de 1024 a 104857600.|El valor predeterminado es 102400.|  
|PollingInterval|VT_UI4|Especificar el intervalo en milisegundos con el que el adaptador de archivo efectuará el sondeo de la ubicación especificada en busca de nuevos archivos.|Los valores válidos son de 1000 a 3600000.|Establecer en 1 para deshabilitar el sondeo.|  
|BatchSize|VT_UI4|Especificar el número máximo de mensajes que se va a enviar en un lote.|Los valores válidos son de 1 a 256.|El valor predeterminado es 20.|  
|FileNetFailRetryInt|VT_UI4|Especificar el tiempo de intervalo de reintentos (en minutos) entre los intentos de obtención de acceso a la ubicación de recepción del recurso compartido de red que no está disponible temporalmente.|Los valores válidos son de 0 a 4294967295.|El valor predeterminado es 5.|  
|RemoveReceivedFileDelay|VT_UI4|Especificar el intervalo inicial en milisegundos que esperará el adaptador de archivo antes de intentar eliminar un archivo que ha leído y enviado a BizTalk Server.|Este intervalo se duplicará después de cada intervalo de reintento hasta alcanzar el valor máximo de intervalo de reintento.<br /><br /> Los valores válidos son de 1 a 1000.|El valor predeterminado es 10.|  
|RenameReceivedFiles|VT_BOOL|Especificar si se cambiará el nombre de los archivos antes de seleccionarlos para su procesamiento.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0.|  
|FileNetFailRetryCount|VT_UI4|Especificar el número de intentos de obtención de acceso a la ubicación de recepción de un recurso compartido de red que no está disponible temporalmente.|Los valores válidos son de 0 a 4294967295.|El valor predeterminado es 5.|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<RemoveReceivedFileRetryCount vt="19">5</RemoveReceivedFileRetryCount>  
<RemoveReceivedFileMaxInterval vt="19">300000</RemoveReceivedFileMaxInterval>  
<FileMask vt="8">*.xml</FileMask>  
<BatchSizeInBytes vt="19">102400</BatchSizeInBytes>  
<PollingInterval vt="19">60000</PollingInterval>  
<BatchSize vt="19">20</BatchSize>  
<FileNetFailRetryInt vt="19">5</FileNetFailRetryInt>  
<RemoveReceivedFileDelay vt="19">10</RemoveReceivedFileDelay>  
<RenameReceivedFiles vt="11">0</RenameReceivedFiles>  
<FileNetFailRetryCount vt="19">5</FileNetFailRetryCount>  
</CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de archivo:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|Nombre de usuario|VT_BSTR|Especifica credenciales alternativas cuando la instancia de host del adaptador de archivo no tiene los derechos necesarios para un recurso compartido de red.|Ninguno|Especifique el nombre de usuario con el formato \<dominio > \username.|  
|UseTempFileOnWrite|VT_BOOL|Especifica que se utilizará un archivo temporal al escribir en la carpeta de destino. Una vez que se termina de escribir, se le cambia el nombre al valor especificado para la propiedad Nombre de archivo.|Esta propiedad solo puede establecerse como -1 (verdadero) si la propiedad CopyMode se establece con el valor 2 (Crear nuevo).<br /><br /> Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|CopyMode|VT_UI4|Definir el modo de copia que se utilizará al escribir un mensaje en un archivo|Los valores válidos son:<br /><br /> -0 (anexar)<br />-1 (sobrescribir)<br />-2 (crear nuevo)|El valor predeterminado es 2 (Crear nuevo).|  
|FileName|VT_BSTR|Especificar el nombre de archivo en el que el controlador de envío de archivos escribe el mensaje.|Para obtener información acerca de las restricciones en esta propiedad, vea [restricciones en las propiedades de nombre de archivo y la máscara de archivo](http://msdn.microsoft.com/library/d8f5afd0-a61f-4c9b-8a57-4792e3054769).|El valor predeterminado es %MessageID%.xml.|  
|AllowCacheOnWrite|VT_BOOL|Especifica si se utiliza el almacenamiento en caché del sistema de archivos al escribir un mensaje en un archivo.|Los valores válidos son:<br /><br /> -0 (no se usa el almacenamiento en caché)<br />--1 (use el almacenamiento en caché)|El valor predeterminado es 0 (no utilizar almacenamiento en caché).|  
|Contraseña|VT_NULL|Especifica la contraseña utilizada junto con la propiedad Username cuando la instancia de host del adaptador de archivo no tiene los derechos necesarios para un recurso compartido de red.|Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Ninguno|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<Username vt="8">Domainname\User</Username>  
<UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
<CopyMode vt="19">1</CopyMode>  
<FileName vt="8">%MessageID%.xml</FileName>  
<AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
<Password vt="1" />  
</CustomProps>  
```
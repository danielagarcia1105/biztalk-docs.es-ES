---
title: Crear mediante programación el archivo de ubicación de recepción o puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 558a414c-60bc-4f62-9397-a023ed4937fb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 424c2c61655da599c4f437d3fdbf200df29d4e13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013717"
---
# <a name="programmatically-create-the-file-receive-location-or-send-port"></a>Crear mediante programación el archivo de ubicación de recepción o puerto de envío
Cómo crear un archivo de puerto de recepción y puerto de envío mediante programación. Para usar el [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], vaya a [configurar el adaptador de archivo](../core/configure-the-file-adapter.md).

El adaptador de archivo almacena la información de configuración en la base de datos de SSO. Puede configurar las ubicaciones de recepción y el Explorador de BizTalk mediante programación a través de puertos de envío de modelo de objetos. 
 
## <a name="create-the-receive-location"></a>Crear la ubicación de recepción

El modelo de objetos del explorador de BizTalk expone la **IReceiveLocation** interfaz de configuración que contiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta la bolsa de propiedades de configuración de la ubicación de recepción de archivo en forma de cadena XML de par nombre/valor.  
  
El **TransportTypeData** propiedad de la **IReceiveLocation** interfaz no tiene que establecerse. Si no se define, se utilizan los valores predeterminados de la configuración de la ubicación de recepción de archivo.  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir mediante programación para la ubicación de recepción de archivo.  
  
|Nombre de propiedad|Tipo|Descripción|Restrictions|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|**FileNetFailRetryCount**|Long|Número de intentos de obtención de acceso a la ubicación de recepción del recurso compartido de red si no se encuentra disponible temporalmente.|Integer<br /><br /> Valor mínimo: 0<br /><br /> Valor máximo: MAX_LONG|Si no se especifica, se establece 5 veces como valor predeterminado.|  
|**FileNetFailRetryInterval**|Long|Intervalo de reintento en minutos entre los intentos para obtener acceso a la ubicación de recepción del recurso compartido de red que, temporalmente, no se encuentra disponible.|Integer<br /><br /> MinimumValue: 0<br /><br /> Valor máximo: MAX_LONG|Si no se especifica, se establece 5 minutos como valor predeterminado.|  
|**BatchSize**|Long|Número de archivos que la ubicación de recepción puede enviar al servidor de una sola vez.|Integer<br /><br /> Valor mínimo: 1<br /><br /> Valor máximo: 256|Si no se especifica, se establece 20 archivos como valor predeterminado.|  
|**FileMask**|String|Máscara de archivo que utiliza la ubicación de recepción.|String<br /><br /> La longitud de la combinación de FilePath y FileMask no puede superar los 256 caracteres.|Si no se especifica, se establece *.xml como valor predeterminado.|  
|**FilePath**|String|Ruta de la carpeta supervisada por la ubicación de recepción.|String<br /><br /> Obligatorio<br /><br /> La longitud de la combinación de FilePath y FileMask no puede superar los 256 caracteres.|Debe especificarse **importante:** la carpeta de archivos creada para la ubicación de recepción debe tener permiso de escritura para las credenciales de controlador de recepción configuradas en la ubicación de recepción.|  
|**Nombre de usuario**|String|Nombre de usuario de la cuenta utilizada para obtener acceso a la carpeta.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Si no especifica el nombre de usuario ni la contraseña, se usarán las credenciales del host.<br /><br /> Si es nulo (vt=”1”), se usa el valor almacenado en la base de datos de configuración.|  
|**Contraseña**|String|Contraseña para la cuenta utilizada para obtener acceso a la carpeta.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Si no especifica el nombre de usuario ni la contraseña, se usarán las credenciales del host.<br /><br /> Si es nulo (vt=”1”), se usa el valor almacenado en la base de datos de configuración.|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
   <FilePath vt="8">C:\Temp</FilePath>  
   <BatchSize vt="19">20</BatchSize>  
   <FileMask vt="8">*.xml</FileMask>  
   <FileNetFailRetryCount vt="19">5</FileNetFailRetryCount>  
   <FileNetFailRetryInterval vt="19">5</FileNetFailRetryInterval>  
   <Username vt=”8”>MyDomain\MyUsername</Username>  
   <Password vt=”8”>PASSWORD</Password>  
</CustomProps>  
  
```  

## <a name="create-the-send-port"></a>Crear el puerto de envío

La información de configuración se almacena en la bolsa de propiedades XML personalizada. El `bts_file_properties.xsd` esquema de propiedades de controlador de envío de archivo define las propiedades específicas del adaptador de archivo. Estas propiedades se utilizan para configurar los puertos de envío de archivo y pasar la información específica del adaptador por el servidor.  
  
El modelo de objetos del explorador de BizTalk expone la **ITransportInfo** interfaz de configuración de adaptador para puertos de envío de archivo, que contiene el **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta la bolsa de propiedades de configuración del controlador de envío de archivo como una cadena XML de par de nombre y valor.  
  
 Establecer el **TransportTypeData** propiedad de la **ITransportInfo** interfaz no es necesaria. Si no se define, se utilizan los valores predeterminados de la configuración del controlador de envío de archivo.  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir de forma programada en el modelo de objetos del Explorador de BizTalk para la ubicación del controlador de envío de archivo.  
  
|Nombre de propiedad|Tipo|Descripción|  
|-------------------|----------|-----------------|  
|**CopyMode**|Long|Definir el modo de copia que se usará al escribir un mensaje en un archivo. Los valores válidos son:<br /><br /> **Append (0).** El controlador de envío de archivo abre un archivo, si existe, y anexa un mensaje al final del archivo. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.<br /><br /> **Crear nuevo (1).** Si el archivo no existe, el controlador de envío de archivo crea un archivo nuevo y lo escribe. Si el archivo ya existe, el controlador de envío de archivo notifica un error y sigue la lógica de reintento de adaptador común para los puertos de envío. Éste el modo de copia predeterminado para el controlador de envío de archivo.<br /><br /> **Sobrescribir (2).** El controlador de envío de archivo abre un archivo, si existe, y sobrescribe su contenido. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.|  
|**AllowCacheOnWrite**|Boolean|Define si el adaptador de archivo utiliza el almacenamiento en caché del sistema de archivos al escribir un mensaje en un archivo.<br /><br /> Los valores válidos son:<br /><br /> **True (-1)** el adaptador de archivo utiliza el almacenamiento en caché del sistema de archivos al escribir el archivo de salida.<br /><br /> **False (0)** controlador de envío del archivo no usa el almacenamiento en caché del sistema de archivos al escribir el archivo de salida.|  
|**Utilizar un archivo temporal mientras se escribe**|Boolean|Define si se debe escribir el archivo de resultados en un archivo temporal en primer lugar y, a continuación, cambiar el nombre del archivo una vez que se ha completado la operación de escritura. Si esta opción está habilitada, se creará el archivo temporal con la extensión **BTS-WIP**.<br /><br /> Los valores válidos son:<br /><br /> **True (-1)** el adaptador de archivo crea un archivo temporal cuando se escribe en la carpeta de destino.<br /><br /> **False (0)** el adaptador de archivo no crea un archivo temporal cuando se escribe en la carpeta de destino. **Nota:** esta opción solo está disponible cuando el **CopyMode** propiedad está establecida en un valor de **crear nuevo (1)**.|  
  
 Si ninguna de las propiedades de configuración tiene un valor de contexto de mensaje, el controlador de envío de archivo utiliza el valor predeterminado.  
  
 Puede establecer propiedades de configuración mediante programación en un contexto de mensaje. Puede establecer estas propiedades en una orquestación o un componente de canalización personalizado. Las reglas siguientes se aplican cuando se utilizan estas propiedades:  
  
- Si la propiedad de configuración se establece en una orquestación o en un componente de canalización personalizado de una canalización de recepción, entonces:  
  
  -   Si se envía un mensaje a un puerto de envío estático, el valor de la propiedad se sobrescribirá con el valor configurado para dicho puerto de envío.  
  
  -   Si el mensaje se envía a un puerto de envío dinámico, el valor de la propiedad no se sobrescribirá.  
  
- Si una propiedad de configuración se establece en un componente de canalización personalizado en una canalización de envío, entonces:  
  
  -   El valor no se sobrescribirá independientemente de que el mensaje se envíe a un puerto de envío estático o dinámico.  
  
  En el siguiente código se muestra el formato de la cadena XML que puede utilizar para establecer las propiedades:  
  
```  
<CustomProps>  
   <CopyMode vt="19">0</CopyMode>  
   <AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
   <UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
</CustomProps>  
```  



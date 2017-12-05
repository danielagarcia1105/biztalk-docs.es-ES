---
title: "Propiedades de configuración del adaptador de MQSeries | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, code sample
- receive locations, adapters
- MQSeries adapters, send ports
- MQSeries adapters, properties
- MQSeries adapters, receive location
- send ports, adapters
ms.assetid: 7517a8bf-aa65-4af9-aed0-7c74fb480328
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f7c24f15c916970926143cec4cb6bb33401efeb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="mqseries-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de MQSeries
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir mediante una ubicación de recepción del adaptador de MQSeries:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|Especificar la ruta completa a la ubicación supervisada por la ubicación de recepción.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|queueDetails|VT_BSTR|Especifica información acerca de la cola de MQSeries de origen que incluye servidor, administrador de cola y cola.|-Ninguno|Esta propiedad se antepone a MQS:// para crear la propiedad URI.|  
|transactionSupported|VT_BSTR|Especifica si el adaptador de MQSeries inicia una transacción del Coordinador de transacciones distribuidas de Microsoft (DTC) entre BizTalk Server y el servidor MQSeries.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|Cuando se establece en no, no hay ninguna garantía de entrega de mensajes.<br /><br /> El valor predeterminado es Yes.|  
|suspendAsNonResumable|VT_BSTR|Especificar si los mensajes suspendidos se marcan o no como reanudables.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|El valor predeterminado es no.|  
|dataOffsetForHeaders|VT_BSTR|El adaptador utiliza valores de los encabezados de MQSeries (las estructuras MQXQH, MQIIH y MQCIH) para rellenar los valores correspondientes en las propiedades de contexto de BizTalk Server. De forma predeterminada, el adaptador quita estas propiedades de MQSeries del cuerpo del mensaje.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|Establezca esta propiedad en no para mantener estas propiedades en el cuerpo del mensaje.<br /><br /> El valor predeterminado es Yes.|  
|pollingInterval|VT_BSTR|Especifica el intervalo usado por el componente de recepción para sondear la cola de MQSeries.|Los valores válidos son de 1 a 10000.|pollingInterval actúa en combinación con el intervalo de espera codificado de tres segundos que está integrado en el adaptador. Si el valor pollingInterval es inferior a tres (3) segundos, el intervalo de espera se establece como el valor de pollingInterval.<br /><br /> El valor predeterminado es 3.|  
|pollingUnit|VT_BSTR|Especifica la unidad de tiempo para el intervalo de sondeo.|Los valores válidos son:<br /><br /> -horas<br />-minutos<br />-segundos|El valor predeterminado es segundos.|  
|maximumBatchSize|VT_BSTR|Especifica el tamaño máximo de un lote de mensajes en kilobytes (KB).|Los valores válidos son de 1 a 10485760|El valor predeterminado es 100.|  
|maximumNumberOfMessages|VT_BSTR|Especifica el número máximo de mensajes en un lote.|Los valores válidos son de 1 a 100000|El valor predeterminado es 100.|  
|threadCount|VT_BSTR|Especifica el número de subprocesos que se utilizan por ubicación de recepción.|Los valores válidos son de 1 a 64.|El valor predeterminado es 2.|  
|fragmentationSize|VT_BSTR|Especifica el tamaño del fragmento de mensaje en kilobytes (KB) para los mensajes a medida que se envían entre MQSAgent y el adaptador.|Los valores válidos son de 1 a 1048576.|El valor predeterminado es 500.|  
|characterSet|VT_BSTR|Especifica el juego de caracteres y si MQSeries convierte los caracteres antes de enviar el mensaje a la ubicación de recepción.|Los valores válidos son:<br /><br /> -Ninguno. No convertir.<br />-UCS-2 y UTF-16. Convertir a estos conjuntos de caracteres. MQSeries no distingue un juego de otro.<br />UTF-8. Convertir al juego de caracteres UTF-8.|El valor predeterminado es Ninguno.|  
|errorThreshold|VT_BSTR|Especifica el número máximo de errores que se deben registrar. El adaptador continúa funcionando y, si se recupera, registra el suceso en el registro de sucesos.|Los valores válidos son de 1 a 1000.|El valor predeterminado es 10.|  
|segmentación|VT_BSTR|Especifica si MQSeries ensambla los mensajes segmentados u obtiene los mensajes tal como están.|Los valores válidos son:<br /><br /> -Ninguno<br />-completo|Especificar Ninguno para leer mensajes de la cola MQSeries sin habilitar la segmentación.<br /><br /> Especificar Completa para que MQSeries ensamble mensajes segmentados antes de pasarlos al adaptador.<br /><br /> El valor predeterminado es Ninguno.|  
|ordenadas|VT_BSTR|Especifica si MQSeries mantiene el orden de los mensajes a medida que se reciben de la cola MQSeries.|Los valores válidos son:<br /><br /> -ninguna<br />-noStop<br />-yesStop<br />-yesSuspend|Especificar No para no tener en cuenta el orden de los mensajes.<br /><br /> Especificar noStop para no tener en cuenta el orden de los mensajes y deshabilitar la ubicación de recepción si hay un error.<br /><br /> Especificar yesStop para habilitar el ordenamiento. Esta opción finaliza la transacción y deshabilita la ubicación de recepción si hay un error.<br /><br /> Especificar yesSuspend para habilitar el ordenamiento. Esta opción mueve el mensaje a la cola de suspensión cuando hay un error. Este valor no mantiene el orden cuando hay un error, pero permite que la ubicación de recepción continúe recibiendo mensajes.<br /><br /> El valor predeterminado es no.|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1/RQ0</uri><queueDetails>TESTMQServer/DQM1/RQ0</queueDetails><transactionSupported>yes</transactionSupported><suspendAsNonResumable>no</suspendAsNonResumable><dataOffsetForHeaders>yes</dataOffsetForHeaders><pollingInterval>1</pollingInterval><pollingUnit>seconds</pollingUnit><maximumBatchSize>100</maximumBatchSize><maximumNumberOfMessages>100</maximumNumberOfMessages><threadCount>2</threadCount><fragmentationSize>500</fragmentationSize><characterSet>none</characterSet><errorThreshold>10</errorThreshold><segmentation>none</segmentation><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir mediante un puerto de envío del adaptador de MQSeries:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|Especificar la ruta completa de la ubicación a la que enviar datos.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Ninguno|  
|queueDetails|VT_BSTR|Especifica información acerca de la cola de MQSeries de destino que incluye servidor, administrador de cola y cola.|La URI de un puerto de envío o ubicación de recepción no puede superar los 256 caracteres.|Esta propiedad se antepone a MQS:// para crear la propiedad URI.|  
|transactionSupported|VT_BSTR|Especifica si el adaptador de MQSeries inicia una transacción del Coordinador de transacciones distribuidas de Microsoft (DTC) entre BizTalk Server y el servidor MQSeries.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|Cuando se establece en no, no hay ninguna garantía de entrega de mensajes.<br /><br /> El valor predeterminado es Yes.|  
|dataConversion|VT_BSTR|Especifica si se convierte el mensaje a la página de códigos ANSI de MQSeries para Windows Server.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|El valor predeterminado es no.|  
|segmentationAllowed|VT_BSTR|Especifica si se usará la segmentación del administrador de cola MQSeries cuando un mensaje concreto supera la longitud máxima de mensajes de la cola MQSeries.|Valores válidos son:<br /><br /> -Sí<br />-ninguna|El valor predeterminado es no.|  
|fragmentationSize|VT_BSTR|Especifica el tamaño del fragmento de mensaje en kilobytes (KB) para los mensajes a medida que se envían entre el adaptador y MQSAgent.|Los valores válidos son de 1 a 1048576.|El valor predeterminado es 500.|  
|ordenadas|VT_BSTR|Especifica si MQSeries mantiene el orden de los mensajes a medida que se envían a la cola MQSeries.|Los valores válidos son:<br /><br /> -Sí<br />-ninguna|El valor predeterminado es no.|  
  
 En el siguiente código se muestra el formato de la cadena que se utiliza para establecer las propiedades:  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1(QM1)/SQ0</uri><queueDetails>TESTMQServer/DQM1(QM1)/SQ0</queueDetails><transactionSupported>yes</transactionSupported><dataConversion>no</dataConversion><segmentationAllowed>no</segmentationAllowed><fragmentationSize>500</fragmentationSize><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  Al especificar los datos de configuración de TransportTypeData para un adaptador que se genera utilizando el marco de trabajo, los pares de nombre/valor que se usan todos se almacenarán en el \<AdapterConfig\> elemento. Puesto que la \<AdapterConfig\> elemento especifica la VT_BSTR (vt = "8"), a continuación, el tipo de datos de la \< \> caracteres en los datos deben convertirse.
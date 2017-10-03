---
title: "Configuración del adaptador de HTTP y parámetros de ajuste | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, parameters
- configuring [HTTP adapters], parameters
- HTTP adapters, tuning
- RequestQueueSize key [HTTP adapters]
- HttpReceiveThreadsPerCpu key [HTTP adapters]
- HttpOutTimeoutInterval key [HTTP adapters]
- HttpOutInflightSize key [HTTP adapters]
- configuring [HTTP adapters], tuning
- DisableChunkEncoding key [HTTP adapters]
- HttpOutCompleteSize key [HTTP adapters]
ms.assetid: c8989a88-722a-40b5-94cf-4b6840add02e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db4f4dc4403ddfbf677ac2729c00e2b1976db61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-configuration-and-tuning-parameters"></a>Configuración del adaptador de HTTP y parámetros de ajuste
Puede tener acceso a varios parámetros de configuración y ajuste del adaptador de HTTP mediante entradas de clave del Registro, y mediante la modificación del archivo BTSNTSvc.exe.config (ubicado en el directorio raíz de instalación de BizTalk Server).  
  
 **Configuración del registro que afectan al rendimiento del adaptador HTTP**  
  
 La tabla siguiente describe los valores de configuración del Registro que afectan al rendimiento del adaptador de HTTP. Tenga en cuenta que, de forma predeterminada, el Registro no contiene claves del adaptador de HTTP, por lo que dicho adaptador utiliza la configuración predeterminada. Si es necesario cambiar la configuración predeterminada, deberá crear estas claves del Registro en las siguientes ubicaciones del Registro:  
  
-   **DisableChunkEncoding**, **RequestQueueSize**, y **HttpReceiveThreadsPerCpu** debe definirse en **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ BTSSvc.3.0\HttpReceive**.  
  
-   **HttpOutTimeoutInterval**, **HttpOutInflightSize**, y **HttpOutCompleteSize** debe definirse en **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ BTSSvc {GUID}** donde **GUID** es el identificador del host para el controlador de envío HTTP.  
  
|Nombre de clave|Tipo|Predeterminado|Explicación|  
|--------------|----------|-------------|-----------------|  
|**DisableChunkEncoding**|DWORD|0|Determina si el adaptador de recepción HTTP debe o no utilizar una codificación fragmentada al enviar las respuestas al cliente.<br /><br /> Debe definirse con un valor distinto de cero para desactivar la codificación fragmentada en las respuestas del adaptador de recepción HTTP.<br /><br /> **Valor mínimo:** 0<br /><br /> **Valor máximo:** cualquier valor distinto de cero|  
|**RequestQueueSize**|DWORD|256|Define el número de solicitudes que el adaptador de recepción HTTP puede procesar de forma simultánea.<br /><br /> **Valor mínimo:** 10<br /><br /> **Valor máximo:** 2048|  
|**HttpReceiveThreadsPerCpu**|DWORD|2|Define el número de subprocesos por CPU que se asignan al adaptador de recepción HTTP.<br /><br /> **Valor mínimo:** 1<br /><br /> **Valor máximo:** 10|  
|**HttpOutTimeoutInterval**|DWORD|2000|Define el tiempo (en segundos) que esperará el adaptador de envío HTTP antes de que se exceda el tiempo de espera.<br /><br /> **Valor mínimo:** 500<br /><br /> **Valor máximo:** 10000000.|  
|**HttpOutInflightSize**|DWORD|100|Número máximo de solicitudes de HTTP que podrá administrar de forma simultánea una instancia del adaptador de envío HTTP de BizTalk Server.<br /><br /> El valor recomendado para la latencia es entre 3 y 5 veces el **maxconnection** entrada del archivo de configuración se describe a continuación.<br /><br /> **Valor mínimo:** 1<br /><br /> **Valor máximo:** 1024|  
|**HttpOutCompleteSize**|DWORD|5|Controla el tamaño del lote de mensajes que se devuelve desde el adaptador de envío HTTP. Si el búfer no está lleno y hay respuestas pendientes, a continuación, el adaptador esperará 1 segundo hasta que confirma el lote.  Para escenarios de baja latencia se debe establecer en 1 que permitirá al adaptador enviar los mensajes de respuesta inmediatamente en el cuadro de mensajes para procesar.<br /><br /> **Valor mínimo:** 1<br /><br /> **Valor máximo:** 1024|  
  
 **Entrada del archivo de configuración que controla el número de conexiones simultáneas efectuadas por el adaptador de envío HTTP para un determinado servidor de destino**  
  
 El número de conexiones simultáneas que puede abrir el adaptador de HTTP para un determinado servidor de destino se configura insertando una entrada en el archivo de configuración BTSNTSvc.exe.config, que se encuentra en el directorio raíz de instalación de BizTalk Server.  
  
> [!NOTE]
>  Esta propiedad se aplicará a los adaptadores de HTTP y de SOAP cuando envíen mensajes al mismo servidor HTTP de destino. El valor predeterminado para la propiedad “maxconnnection” es 2, el valor máximo que se puede establecer para la propiedad “maxconnection” para todos los URI es 20.  
  
 El siguiente ejemplo muestra la configuración de la propiedad de número máximo de conexiones:  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "20" />  
      <add address = "http://www.northwind.com" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador HTTP](../core/configuring-the-http-adapter.md)
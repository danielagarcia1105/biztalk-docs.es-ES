---
title: "¿Qué &#39; s nuevo acelerador de BizTalk para HL7 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new
- BizTalk Accelerator for HL7, what's new
- getting started, what's new
ms.assetid: e98595a1-2d1e-488e-8a97-7cd561948b3b
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c350ef616acf61cab7910c5381cca02d68c919f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what39s-new-in-biztalk-accelerator-for-hl7"></a>¿Qué &#39; s nuevo acelerador de BizTalk para HL7
Cambios y actualizaciones con la [!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]. 

## <a name="biztalk-server-2016"></a>BizTalk Server 2016

|Característica|Description|  
|---|---| 
| **Inicia la conexión LOB** | Mediante el adaptador MLLP, [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] puede iniciar o iniciar la conexión a un sistema remoto de servidor (LOB) de línea de negocio. LOB esperará a que la conexión y, a continuación, envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] con el adaptador MLLP. Hay algunas propiedades de nuevo en la MLLP ubicación de recepción que configure esta opción. Vea: <br/><ul><li>[Paso 4 del tutorial de extremo a extremo](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)</li><li>[Paso 4 del tutorial interrogative](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)</li><li>[Paso 5 del tutorial interrogative](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)</li><li>[Paso 4 del tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)</li></ul>En [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores, el MLLP HL7 adaptador esperará a que el servidor remoto de LOB conectar con el adaptador MLLP de recepción y, a continuación, el LOB envía mensajes. <br/><br/>Vea [cómo BTAHL7 enruta los mensajes](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md) para obtener más detalles.|

## <a name="biztalk-server-2013-r2"></a>BizTalk Server 2013 R2  
  
|Característica|Description|  
|-------------|-----------------|  
|**compatibilidad con 64 bits**|Los adaptadores MLLP y la canalización de HL7 pueden ejecutarse en las instancias de host de 32 bits y 64 bits.<br /><br /> El [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] instalación incluye un paquete de instalación de 32 bits y un paquete de instalación de 64 bits. En un equipo de 32 bits, instale únicamente el paquete de 32 bits. En un equipo de 64 bits, instale lo 32 bits **o** paquete de 64 bits. <br/><br/>**Importante:** para usar la compatibilidad con 64 bits, solo puede instalar el paquete de 64 bits. El paquete de 64 bits permite que el adaptador y las canalizaciones se ejecuten en modo de 32 bits y de 64 bits.|  
|**compatibilidad con el esquema v2.6**|La compatibilidad incluye:<br /><br /> -   **BTAHL7V26Common** proyecto: incluye los esquemas v2.6.<br />-   **BTAHL7Common** proyecto: incluye los esquemas v2.6 y el esquema de confirmación ACK_26_GLO_DEF; que genera la confirmación para los mensajes de v2.6.<br />-   **MSH_25_GLO_DEF** esquema: identificadores de los campos de encabezado que se incluyen con el esquema v2.6 y sigue siendo compatible con v2 todos los mensajes nuevos. *x* esquemas.|  
|**Compatibilidad del adaptador MLLP dinámica**|Puerto de envío del adaptador de propiedades se pueden configurar en tiempo de ejecución mediante un unidireccional o bidireccional (solicitud-respuesta). Vea [adaptador MLLP dinámico](../../adapters-and-accelerators/accelerator-hl7/dynamic-mllp-adapter.md).|  
|**Compatibilidad con "FreeText"**|Si un campo o un segmento se define como "FreeText", no se analizan los datos de caracteres en el segmento de campo. Vea [codificación de caracteres con texto sin formato](../../adapters-and-accelerators/accelerator-hl7/encoding-characters-using-free-text.md).|  
|**Se envían mensajes con MSH válido un ACK o NACK**|Mediante el **ReturnErrorForInvalidMSH3** clave del registro, se envía una confirmación negativa (NACK) a la entidad si ocurre lo siguiente:<br /><br /> -MSH3 no válido (entidad no está definida en el Explorador de configuración de HL7) <br />    **AND**<br />-Valores de MSH15 y MSH16 en el mensaje son null ni estar vacío<br /><br /> Para enviar NACK, establezca la siguiente clave del registro en 1 y, a continuación, reinicie la instancia de host:<br /><br /> host de 32 bits:`HKLM\SOFTWARE\Microsoft\BizTalk Accelerator for HL7`<br /><br /> host de 64 bits:`HKLM\ SOFTWARE\Wow6432Node\Microsoft\BizTalk Accelerator for HL7` <br/><br/>**Sugerencia:** un puerto puede suscribirse al mensaje de error: <ul><li>Use la **BTAHL7Schemas.ParseError = True** condición de filtrado.</li><li>Use la **Pass Through** canalización.</li></ul>|  
|**Instancia de mensaje de confirmación permanece activo**|Si se produce el error de conexión en el sistema de nivel superior, la confirmación (ACK) que se envía al sistema de nivel superior permanece en estado activo.<br /><br /> Nuevo comportamiento: Si hay un error de conexión con el sistema de nivel superior, se suspende el mensaje de confirmación.|  
|**No enviar \<SB >**|Esta propiedad se agrega a las propiedades de configuración de puerto del adaptador de recepción. Para habilitar esta propiedad, establezca el **UseMLLPTransACK** valor:<br /><br /> -Cuando se establece en **False** (valor predeterminado), el adaptador envía el mensaje si los datos comienzan con \<SB >. Por ejemplo, se envía el mensaje siguiente:<br /> `<SB\>DataData<CR\>DataData<CR\>…`<br/><br />-Cuando se establece en **True**, el adaptador envía el mensaje si los datos no se encuentra \<SB > al principio. Por ejemplo, se envía el mensaje siguiente:<br /> `DataData<CR\>DataData<CR\>…` <br/><br/>**Importante:** si una forma puerto de envío tiene **no enviar \<SB >** establecida en True, no enviará SB con el mensaje en el sistema de nivel inferior. Al mismo tiempo que puede recibir confirmación con la que falta SB desde el sistema de nivel inferior.|  
|**Aceptar falta \<SB >**|Esta propiedad se agrega a las propiedades de configuración de puerto del adaptador de envío. Para habilitar esta propiedad, establezca el **UseMLLPTransACK** valor:<br /><br /> -Cuando se establece en **False** (valor predeterminado), el adaptador devuelve un error si los datos no se encuentra \<SB > al principio. Por ejemplo, el mensaje siguiente devuelve un error:<br /> `DataData<CR\>DataData<CR\>…`<br/><br />-Cuando se establece en **True**, el adaptador puede recibir el mensaje si los datos no se encuentra \<SB > al principio. Por ejemplo, se reciben los mensajes siguientes:<br /> `<SB\>DataData<CR\>DataData<CR\>…` <br />`DataData<CR\>DataData<CR\>…` <br/><br/>**Importante:** si una forma puerto de recepción tiene **Aceptar falta \<SB >** establecida en True, aceptará el SB falta en el mensaje del sistema de nivel superior. Al mismo tiempo no enviará SB en el sistema de nivel superior.|  
  
## <a name="biztalk-server-2013"></a>BizTalk Server 2013  
  
 Se incluyen las siguientes mejoras en las versiones anteriores:  
  
-   Compatibilidad de intercambio recuperable en canalización HL7 para en lote Out escenario de lote.  
  
 En las versiones anteriores, se quitó la siguiente característica:  
  
-   Característica de seguimiento de actividad de mantenimiento se quita del servidor BizTalk Server y, por tanto, se quita la característica de auditoría de BTAHL7 pero registro permanece intacto.  
  
 La siguiente función se modificó en las versiones anteriores:  
  
-   Se cambia el nombre "Auditoría y registro de servicio", "Servicio de registro HL7".  

## <a name="see-also"></a>Vea también

[Novedades en BizTalk Server 2016](../../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
[Novedades de BizTalk Server 2013 R2 y 2013](../../install-and-config-guides/what-s-new-in-biztalk-server-2013-and-2013-r2.md)
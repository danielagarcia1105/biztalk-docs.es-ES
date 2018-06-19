---
title: Propiedades de contexto de MQSeries | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQCIH_TaskEndStatus property [MQSeries adapters]
- MQIIH_SecurityScope property [MQSeries adapters]
- MQCIH_AbendCode property [MQSeries adapters]
- filters, MQSeries adapters
- MQCIH_ReturnCode property [MQSeries adapters]
- MQCIH_TransactionId property [MQSeries adapters]
- MQCIH_ReplyToFormat property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- MQMD_PutTime property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQMD_PutApplName property [MQSeries adapters]
- configuring [MQSeries adapters], filtering
- MQCIH_UOWControl property [MQSeries adapters]
- MQCIH_ErrorOffset property [MQSeries adapters]
- MQMD_Priority property [MQSeries adapters]
- MQMD_MsgSeqNumber property [MQSeries adapters]
- MQMD_Format property [MQSeries adapters]
- MQCIH_ConversationalTask property [MQSeries adapters]
- Message Descriptor table [MQSeries adapters]
- MQMD_Feedback property [MQSeries adapters]
- MQCIH_Authenticator property [MQSeries adapters]
- MQIIH_TranState property [MQSeries adapters]
- MQCIH_AttentionId property [MQSeries adapters]
- MQMD_UserIdentifier property [MQSeries adapters]
- MQCIH_Flags property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQIIH_Format property [MQSeries adapters]
- MQMD_Offset property [MQSeries adapters]
- MQMD_BackoutCount property [MQSeries adapters]
- MQMD_Report property [MQSeries adapters]
- MQMD_MsgFlags property [MQSeries adapters]
- MQSeries adapters, filtering
- MQMD_ApplIdentityData property [MQSeries adapters]
- MQIIH_Authenticator property [MQSeries adapters]
- MQIIH_MFSMapName property [MQSeries adapters]
- MQCIH_LinkType property [MQSeries adapters]
- MQMD_Persistence property [MQSeries adapters]
- MQCIH_CursorPosition property [MQSeries adapters]
- MQCIH_Format property [MQSeries adapters]
- MQCIH_Facility property [MQSeries adapters]
- MQCIH_CancelCode property [MQSeries adapters]
- MQMD_PutDate property [MQSeries adapters]
- MQCIH_NextTransactionId property [MQSeries adapters]
- MQIIH_CommitMode property [MQSeries adapters]
- MQIIH_ReplyToFormat property [MQSeries adapters]
- MQCIH_Function property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- MQCIH_StartCode property [MQSeries adapters]
- MQMD_Expiry property [MQSeries adapters]
- MQMD_PutApplType property [MQSeries adapters]
- MQCIH_FacilityLike property [MQSeries adapters]
- MQIIH_Flags property [MQSeries adapters]
- MQCIH_CompCode property [MQSeries adapters]
- MQSeries adapters, properties
- MQCIH_FacilityKeepTime property [MQSeries adapters]
- MQMD_ApplOriginData property [MQSeries adapters]
- MQCIH_Reason property [MQSeries adapters]
- MQIIH_LTermOverride property [MQSeries adapters]
- MQMD_CodedCharSetId property [MQSeries adapters]
- MQMD_GroupID property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgType property [MQSeries adapters]
- MQMD_OriginalLength property [MQSeries adapters]
- MQMD_Encoding property [MQSeries adapters]
- MQMD_AccountingToken property [MQSeries adapters]
- MQCIH_OutputDataLength property [MQSeries adapters]
- MQIIH_TranInstanceId property [MQSeries adapters]
- MQCIH_GetWaitInterval property [MQSeries adapters]
- MQCIH_ADSDescriptor property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: 1b22b7d7-432b-4ec5-938c-c43077ce3e0f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d27309379fac2c4821251f27fd2aa5a6e9d59418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266628"
---
# <a name="mqseries-context-properties"></a>Propiedades de contexto de MQSeries
El adaptador de MQSeries proporciona un conjunto de propiedades de contexto, específicas de MQSeries, para su uso en las aplicaciones. Puede utilizar estas propiedades en expresiones de filtro y en las orquestaciones.  
  
 Para asignar propiedades de contexto de MQSeries a un mensaje destinado a un puerto de envío enlazado al adaptador de MQSeries, utilice el operador de asignación de mensajes y especifique una de las propiedades de contexto disponibles en el espacio de nombres de MQSeries.  
  
 El siguiente es un ejemplo de configuración de MQSeries **MQMD_UserIdentifier** propiedad:  
  
```  
Message_2(MQSeries.MQMD_UserIdentifier) = "MeMyselfAndI";  
```  
  
 Se deben obtener valores enumerados de los archivos de encabezado de lenguaje de programación C incluidos en SDK de IBM MQSeries. Estos archivos pueden encontrarse en la carpeta Archivos de programa\IBM\WebSphere MQ\Tools\c\include. Estos archivos definen los valores que se utilizan al establecer o leer valores de propiedades de contexto de MQSeries.  
  
 Los valores de cadenas hexadecimales son cadenas de caracteres que representan valores binarios. No tienen prefijos como 0x. Contienen dígitos que oscilan entre 0 y 9, así como letras entre la "a" y la "f" o la "A" y la "F". El adaptador omite los espacios en blanco de las cadenas.  
  
 Para obtener más información acerca de estas propiedades, vea la documentación de IBM WebSphere MQ.  
  
 En la tabla siguiente se muestra el conjunto completo de propiedades disponibles del descriptor de mensajes (estructura MQMD), así como los valores y tipos correspondientes.  
  
|Nombre|Tipo|Longitud|Valor|  
|----------|----------|------------|-----------|  
|**MQMD_AccountingToken**|string|64|Cadena hexadecimal|  
|**MQMD_ApplIdentityData**|string|32|Cadena hexadecimal|  
|**MQMD_ApplOriginData**|string|4|String<br /><br /> **Valor predeterminado:** espacio|  
|**MQMD_BackoutCount**|unsigned int|4|Number<br /><br /> Sólo lectura<br /><br /> **Valor predeterminado:** 0|  
|**MQMD_CodedCharSetId**|unsigned int|4|Number<br /><br /> **Valor predeterminado:** 0|  
|**MQMD_CorrelId**|string|48|Cadena hexadecimal|  
|**MQMD_Encoding**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado. **Valor predeterminado:** 0|  
|**MQMD_Expiry**|unsigned int|4|Number|  
|**MQMD_Feedback**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado. **Valor predeterminado:** 0|  
|**MQMD_Format**|string|8|String<br /><br /> Si se establece como MQXMIT, asegúrese de que las propiedades de MQXQH tienen valores.|  
|**MQMD_GroupID**|string|48|Cadena hexadecimal|  
|**MQMD_MsgFlags**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado. **Valor predeterminado:** 0|  
|**MQMD_MsgId**|string|48|Cadena hexadecimal|  
|**MQMD_MsgSeqNumber**|unsigned int|4||  
|**MQMD_MsgType**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado.|  
|**MQMD_Offset**|unsigned int|4||  
|**MQMD_OriginalLength**|unsigned int|4||  
|**MQMD_Persistence**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado.|  
|**MQMD_Priority**|unsigned int|4|Number|  
|**MQMD_PutApplName**|string|28|String<br /><br /> **Valor predeterminado:** espacio|  
|**MQMD_PutApplType**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado. **Valor predeterminado:** 0|  
|**MQMD_PutDate**|string|8|Date|  
|**MQMD_PutTime**|string|8|Time|  
|**MQMD_ReplyToQ**|string|48|String<br /><br /> **Valor predeterminado:** espacio|  
|**MQMD_ReplyToQMgr**|string|48|String<br /><br /> **Valor predeterminado:** espacio|  
|**MQMD_Report**|unsigned int|4|Number<br /><br /> Utilice el valor del archivo de encabezado.|  
|**MQMD_UserIdentifier**|string|12|String<br /><br /> Contiene el identificador de usuario cuando se usa el **SSOAffiliateApplication** propiedad.|  
  
 Al recibir mensajes directamente desde las colas de transmisión MQSeries, el adaptador de MQSeries da formato a las propiedades de encabezado de cola de transmisión (estructura de datos MQXQH) y las coloca en las propiedades de contexto correspondientes. Al enviar mensajes directamente a las colas de transmisión MQSeries, las propiedades de encabezado se da formato y se les asignan valores de la correspondiente contexto propiedades solo si la **MQMD_Format** propiedad tiene un valor de MQXMIT. En la siguiente tabla se describen las propiedades.  
  
|Nombre|Tipo|Longitud|Valor|  
|----------|----------|------------|-----------|  
|**MQXQH_RemoteQMgrName**|string|48|string|  
|**MQXQH_RemoteQName**|string|48|string|  
  
 Junto con las propiedades enumeradas anteriormente en este tema, el adaptador rellena los valores del descriptor de mensajes que se especifican a continuación siguiendo las mismas reglas. El adaptador establece MQXQH_, en lugar de MQMD_, como prefijos de los nombres de propiedad, aunque en caso contrario se asignan directamente a las propiedades definidas en la tabla del descriptor de mensajes:  
  
-   **MQXQH_MsgDesc_AccountingToken**  
  
-   **MQXQH_MsgDesc_ApplIdentityData**  
  
-   **MQXQH_MsgDesc_ApplOriginData**  
  
-   **MQXQH_MsgDesc_BackoutCount**  
  
-   **MQXQH_MsgDesc_CodedCharSetId**  
  
-   **MQXQH_MsgDesc_CorrelId**  
  
-   **MQXQH_MsgDesc_Encoding**  
  
-   **MQXQH_MsgDesc_Expiry**  
  
-   **MQXQH_MsgDesc_Feedback**  
  
-   **MQXQH_MsgDesc_Format**  
  
-   **MQXQH_MsgDesc_MsgId**  
  
-   **MQXQH_MsgDesc_MsgType**  
  
-   **MQXQH_MsgDesc_Persistence**  
  
-   **MQXQH_MsgDesc_Priority**  
  
-   **MQXQH_MsgDesc_PutApplName**  
  
-   **MQXQH_MsgDesc_PutApplType**  
  
-   **MQXQH_MsgDesc_PutDate**  
  
-   **MQXQH_MsgDesc_PutTime**  
  
-   **MQXQH_MsgDesc_ReplyToQ**  
  
-   **MQXQH_MsgDesc_ReplyToQMgr**  
  
-   **MQXQH_MsgDesc_Report**  
  
-   **MQXQH_MsgDesc_UserIdentifier**  
  
 Hay propiedades relacionadas con MQSeries adicionales que se incluyen en el esquema de propiedades y que se encuentran disponibles para utilizarlas en las expresiones de filtro. En la tabla siguiente se enumeran estas propiedades.  
  
|Nombre|Tipo|Longitud|Valor|  
|----------|----------|------------|-----------|  
|**MQCIH_AbendCode**|string|4||  
|**MQCIH_ADSDescriptor**|unsigned int|4||  
|**MQCIH_AttentionId**|string|4||  
|**MQCIH_Authenticator**|string|8|Establecer la contraseña de SSO al usar el **SSOAffiliateApplication** propiedad. **Nota:** este valor se establecerá en blanco por el adaptador de MQSeries si la longitud de la contraseña SSO supera los 8 caracteres.|  
|**MQCIH_CancelCode**|string|4||  
|**MQCIH_CompCode**|unsigned int|4||  
|**MQCIH_ConversationalTask**|unsigned int|4||  
|**MQCIH_CursorPosition**|unsigned int|4||  
|**MQCIH_ErrorOffset**|unsigned int|4||  
|**MQCIH_Facility**|string|16|Cadena hexadecimal|  
|**MQCIH_FacilityKeepTime**|unsigned int|4||  
|**MQCIH_FacilityLike**|string|4||  
|**MQCIH_Flags**|unsigned int|4||  
|**MQCIH_Format**|string|||  
|**MQCIH_Function**|string|4||  
|**MQCIH_GetWaitInterval**|unsigned int|4||  
|**MQCIH_LinkType**|unsigned int|4||  
|**MQCIH_NextTransactionId**|string|4||  
|**MQCIH_OutputDataLength**|unsigned int|4||  
|**MQCIH_Reason**|unsigned int|4||  
|**MQCIH_ReplyToFormat**|string|||  
|**MQCIH_ReturnCode**|unsigned int|4||  
|**MQCIH_StartCode**|string|4||  
|**MQCIH_TaskEndStatus**|unsigned int|4||  
|**MQCIH_TransactionId**|string|4||  
|**MQCIH_UOWControl**|unsigned int|4||  
|**MQIIH_Authenticator**|string|8|Establecer la contraseña de SSO al usar el **SSOAffiliateApplication** propiedad. **Nota:** este valor se establecerá en blanco por el adaptador de MQSeries si la longitud de la contraseña SSO supera los 8 caracteres.|  
|**MQIIH_CommitMode**|string|||  
|**MQIIH_Flags**|unsigned int|4||  
|**MQIIH_Format**|string|||  
|**MQIIH_LTermOverride**|string|8||  
|**MQIIH_MFSMapName**|string|8||  
|**MQIIH_ReplyToFormat**|string|||  
|**MQIIH_SecurityScope**|string|||  
|**MQIIH_TranInstanceId**|string|32|Cadena hexadecimal|  
|**MQIIH_TranState**|string|||  
  
## <a name="see-also"></a>Vea también  
 [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)   
 [Propiedades relacionadas con BizTalk Server](../core/properties-related-to-biztalk-server.md)   
 [Conversión de tipos de datos de propiedades](../core/data-type-conversion-of-properties.md)
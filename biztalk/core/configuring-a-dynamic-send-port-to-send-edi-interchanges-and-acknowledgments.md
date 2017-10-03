---
title: "Configurar un puerto de envío dinámico para enviar intercambios y confirmaciones EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a793fc22394c2b4d294bcd48fae1f9403ae9278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a>Configurar un puerto de envío dinámico para enviar intercambios y confirmaciones EDI
Para enviar una confirmación o intercambio EDI, puede usar un puerto de envío estático o dinámico. Un puerto de envío dinámico permite enviar un intercambio a un destino entre varios, ya que resuelve el acuerdo y determina la dirección de destino en función del valor de la propiedad de contexto DestinationPartyName.  
  
> [!NOTE]
>  Si envía un intercambio EDI basado en un mensaje XML recibido y usa una canalización de recepción tipo "atravesar de" para recibir dicha aplicación, deberá promocionar la propiedad de contexto DestinationPartyName. Para obtener más información, consulte [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).  
  
> [!NOTE]
>  Si el puerto de envío dinámico va a enviar una confirmación, la propiedad de contexto DestinationPartyName ya estará promocionada porque el desensamblador EDI del puerto que ha recibido el intercambio rellena la propiedad DestinationPartyName en la confirmación.  
  
 Para crear un puerto de envío dinámico unidireccional, use la configuración siguiente:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|Unidireccional dinámico|  
|**Propiedades de puerto de envío: General**|Controlador de envío|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de envío|EdiSend|  
|**Propiedades de transporte de archivo: autenticación**|Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red (con nombre de usuario y contraseña)|Definir si se requiere autenticación.|  
|**Propiedades de puerto de envío: filtros**|Propiedad|BTS.MessageType|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|**Para los intercambios**:<br /><br /> - `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, o<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`, o<br /><br /> **Para confirmaciones**:<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, o<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, o<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>Establecimiento de las propiedades del acuerdo  
 Tras la creación del puerto de envío, es necesario establecer las propiedades del acuerdo requeridas para que funcione la canalización de envío. Estas propiedades se establecen en las distintas páginas de la **propiedades del acuerdo de** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución EDI](../core/configuring-ports-for-an-edi-solution.md)
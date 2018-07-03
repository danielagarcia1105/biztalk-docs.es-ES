---
title: Configuración de un puerto de envío estático para mensajes a través de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2708d6a9-b105-42d3-abe3-7085b39da55a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e94514ccd2b16b784e49339f39e9d0c178407b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986605"
---
# <a name="configuring-a-static-send-port-for-messages-over-as2"></a>Configurar un puerto de envío estático para mensajes a través de AS2
En este tema se describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes AS2 a través de un puerto de envío estático. Esta configuración conlleva crear el puerto de envío estático y configurar el acuerdo. Si es necesario, también configurará un certificado de cifrado para que lo use el puerto de envío.  
  
> [!NOTE]
>  En lugar de un puerto de envío estático, puede configurar un puerto de envío dinámico para enviar mensajes AS2. Para obtener más información, consulte [configurar un puerto de envío dinámico para mensajes a través de AS2](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md).  
  
 Para enviar un mensaje AS2 con un mensaje EDI o no EDI o una confirmación EDI, cree un puerto de envío dinámico HTTP de petición-respuesta con la siguiente configuración:  
  
|Ubicación|Property|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|-Estático de petición-respuesta (si solicitar MDN en **confirmaciones (MDN)** está seleccionada la página de la ficha de acuerdo unidireccional)<br /><br /> : Puerto de envío estático unidireccional (si solicitar MDN en **confirmaciones (MDN)** se borra la página de la ficha de acuerdo unidireccional)|  
|**Propiedades de puerto de envío: General**|Tipo de transporte|HTTP<br /><br /> Nota:<br /><br /> Sólo el adaptador HTTP puede utilizarse para transportar mensajes con codificación EDIINT/AS2. Este transporte no funcionará con un adaptador que no sea el adaptador de HTTP.|  
|**Propiedades de puerto de envío: General**|Controlador de envío|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de envío|-AS2EdiSend (para mensajes con codificación EDI)<br /><br /> -AS2Send (para mensajes no pertenecientes a EDI)|  
|**Propiedades de puerto de envío: General**|Controlador de recepción<br /><br /> (si solicitar MDN en **confirmaciones (MDN)** está seleccionada la página de la ficha de acuerdo unidireccional)|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de recepción<br /><br /> (si solicitar MDN en **confirmaciones (MDN)** está seleccionada la página de la ficha de acuerdo unidireccional)|AS2Receive|  
|**Propiedades de transporte HTTP**|Dirección URL de destino|\<Cadena de dirección URL de destino\>|  
|**Propiedades de transporte HTTP**|Habilitar codificación fragmentada|Desactivado|  
|**Propiedades de puerto de envío: filtros**|Property|BTS.MessageType<br /><br /> Nota:<br /><br /> Puede usar diversas expresiones de filtro, como BTS.ReceivePortName.<br /><br /> Nota:<br /><br /> (Para mensajes no pertenecientes a EDI, tendrá que filtrar en una propiedad diferente).|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` (para un mensaje EDI)<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (para un X12 confirmación)<br /><br /> -                   `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` (para una confirmación EDIFACT)|  
|**Propiedades de puerto de envío: certificados**|Nombre común y huella digital|Especifique el nombre del certificado y la huella digital si está usando un certificado de cifrado para el mensaje AS2 saliente.|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-biztalk-server-to-send-as2-messages-over-a-static-send-port"></a>Procedimiento para configurar BizTalk Server para enviar mensajes de AS2 a través de un puerto de envío estático  
  
1. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de envío unidireccional estático o de petición-respuesta estático con la configuración anterior.  
  
2. En la lista de puertos de envío en el **puertos de envío** página de la ficha de acuerdo unidireccional en el **las propiedades del acuerdo** diálogo cuadro, escriba el nombre del puerto de envío estático.  
  
   > [!NOTE]
   >  La configuración del puerto de envío permite a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizar una resolución de acuerdos para un mensaje AS2 saliente.  
  
3. En el **identificadores** página de la ficha de acuerdo unidireccional del **las propiedades del acuerdo** cuadro de diálogo, configure el AS2-a la propiedad para el destino y, a continuación, establezca otras propiedades del acuerdo según sea necesario en el las diferentes páginas de la **las propiedades del acuerdo** cuadro de diálogo.  
  
## <a name="functionality"></a>Funcionalidad  
 El puerto de envío y la canalización realizan lo siguiente para enviar un mensaje o confirmación EDI o no EDI sincrónicos a través de AS2 y procesar el MDN devuelto:  
  
-   Si envía un mensaje EDI, toma el mensaje EDI mediante el filtrado en la propiedad `BTS.MessageType` establecida en el esquema de mensaje en el espacio de nombres de `http://schemas.microsoft.com/BizTalk/EDI/X12/2006` (por ejemplo, X12_00401_864 para un mensaje 864).  
  
-   Si envía una confirmación EDI, toma la confirmación mediante el filtrado en la propiedad `BTS.MessageType` establecida en uno de los siguientes esquemas de control:  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` para una confirmación 997  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` para una confirmación TA1  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` para una confirmación CONTRL  
  
-   Si envía un mensaje no EDI, toma el mensaje mediante el uso de otro filtro.  
  
-   Crea un mensaje AS2. Para obtener más información sobre este proceso, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
-   Envía el mensaje o la confirmación a la URL de destino para el puerto de envío.  
  
-   Recibe la respuesta MDN al mensaje o confirmación, si esta opción está habilitada. Para obtener más información sobre este proceso, consulte [procesar MDN entrantes](../core/processing-an-incoming-mdn.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)   
 [Generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md)   
 [Procesamiento de un MDN de entrada](../core/processing-an-incoming-mdn.md)
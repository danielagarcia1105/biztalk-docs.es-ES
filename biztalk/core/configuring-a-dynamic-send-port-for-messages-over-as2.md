---
title: Configurar un puerto de envío dinámico para mensajes a través de AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6df553a3f03e9d2e60b78de9877ad6113b04e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233892"
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a>Configurar un puerto de envío dinámico para mensajes a través de AS2
En este tema se describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar mensajes AS2 a través de un puerto de envío dinámico. Esta configuración conlleva crear el puerto de envío dinámico y configurar una aplicación de servidor para establecer las propiedades de contexto correctas. Al crear un puerto de envío dinámico para enviar un mensaje AS2, debe promocionar determinadas propiedades para que el puerto de envío funcione. Para obtener más información, consulte [para configurar BizTalk Server para enviar AS2 puerto de envío de mensajes a través de una dinámica](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc) a continuación.  
  
 Un puerto de envío dinámico permite enviar mensajes a varias entidades sin codificar la configuración de la entidad. El acuerdo y el destino que van a usarse en el envío del mensaje se determinan de forma dinámica a través de las propiedades de contexto. No es necesario crear un puerto de envío estático para cada cliente individual.  
  
 Para enviar un mensaje AS2 con un mensaje EDI o no EDI o una confirmación EDI, cree un puerto de envío HTTP de respuesta dinámico con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|-Dinámico de petición-respuesta (si solicitar MDN en **confirmaciones (MDN)** se selecciona la página de la ficha de acuerdo unidireccional)<br /><br /> -Puerto de envío unidireccional dinámico (si solicitar MDN en **confirmaciones (MDN)** se borra la página de la ficha de acuerdo unidireccional)|  
|**Propiedades de puerto de envío: General**|Canalización de envío|-AS2EdiSend (para mensajes con codificación EDI)<br /><br /> -AS2Send (para mensajes no pertenecientes a EDI)|  
|**Propiedades de puerto de envío: General**|Canalización de recepción<br /><br /> (si solicitar MDN en **confirmaciones (MDN)** se selecciona la página de la ficha de acuerdo unidireccional)|AS2Receive (para puertos de envío dinámico de petición-respuesta)|  
|**Propiedades de puerto de envío: filtros**|Propiedad|BTS.MessageType|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>`(para un mensaje EDI)<br /><br /> - `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root`(para un X12 confirmación)<br /><br /> - `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root`(para obtener una confirmación EDIFACT)|  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##  <a name="BKMK_Proc"></a>Para configurar BizTalk Server para enviar AS2 puerto de envío de mensajes a través de una dinámica  
  
1.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de envío unidireccional dinámico (si no se solicita un MDN) o un puerto de envío de petición-respuesta dinámico (si se solicita un MDN) con la configuración anterior.  
  
2.  Para el acuerdo que se aplica a este mensaje, establezca las propiedades de AS2 y de EDI requeridas.  
  
3.  Promocione las siguientes propiedades en el contexto del mensaje:  
  
    -   `BTS.MessageType`  
  
    -   `EdiIntAS.MessageID`  
  
4.  Agregue la funcionalidad a una aplicación de servidor para escribir las siguientes propiedades en el contexto del mensaje y configurarlas con los valores adecuados:  
  
    -   `EdiIntAS.AS2To`  
  
    -   `BTS.OutboundTransportLocation`  
  
    -   `HTTP.EnableChunkedEncoding`  
  
    -   `BTS.EncryptionCert`  
  
    > [!NOTE]
    >  Las propiedades de contexto `AS2To` y `OutboundTransportLocation` deben escribirse en el contexto de mensaje para que el puerto de envío dinámico funcione correctamente. La propiedad `AS2To` se requiere para que el puerto determine la entidad que se va a usar en el procesamiento del mensaje saliente, y la propiedad `OutboundTransportLocation` se requiere para que el puerto de envío determine el destino del mensaje. Para obtener más información, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
## <a name="functionality"></a>Funcionalidad  
 El puerto de envío dinámico y la canalización realizan lo siguiente para enviar un mensaje o confirmación EDI o no EDI sincrónicos a través de AS2 y procesar el MDN devuelto:  
  
-   Si envía un mensaje EDI, toma el mensaje EDI mediante el filtrado en la propiedad `BTS.MessageType` establecida en el esquema de mensaje en el `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` (por ejemplo, X12_00401_864 para un mensaje 864).  
  
-   Si envía una confirmación EDI, toma la confirmación mediante el filtrado en la propiedad `BTS.MessageType` establecida en uno de los siguientes esquemas de control:  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` para una confirmación 997  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` para una confirmación TA1  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` para una confirmación CONTRL  
  
-   Si envía un mensaje no EDI, toma el mensaje mediante el uso de un filtro adecuado.  
  
-   Crea un mensaje AS2. Para obtener más información acerca de este proceso, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el tipo de transporte que va a usarse por el puerto de envío dinámico a partir del formato de la URL, es decir, http, smtp, ftp, etc.  
  
-   Enruta el mensaje o la confirmación a la URL de destino para el puerto de envío.  
  
-   Recibe la respuesta MDN al mensaje o confirmación, si esta opción está habilitada y si se trata de un puerto de envío de petición-respuesta. Para obtener más información acerca de este proceso, consulte [procesamiento de MDN entrante](../core/processing-an-incoming-mdn.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)
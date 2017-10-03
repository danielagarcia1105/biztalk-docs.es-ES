---
title: "Error de configuración. El mensaje de firma &#39; t coincide con el valor esperado. | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0bacd605908abae984247b3d7ed775ea8f5de4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a>Error de configuración. El mensaje de firma &#39; t coincide con el valor esperado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2DecoderPartySigningConfigurationError|  
|Texto del mensaje|Error de configuración. La firma del mensaje no coincide con el valor esperado. Póngase en contacto con el socio remitente y verifique el uso de la firma. AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el componente de descodificador AS2 de la canalización de recepción no pudo procesar el mensaje AS2 porque la firma está especificada en la configuración de la entidad y el mensaje AS2 no está firmado, o bien la firma está especificada para que no se habilite, pero el mensaje está firmado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe que el mensaje AS2 entrante está firmado si la firma está especificada en la configuración de la entidad o bien que el mensaje AS2 entrante no está firmado si la firma está especificada como no habilitada en la configuración de la entidad. Realice una de las siguientes operaciones:  
  
1.  Si el **invalidar propiedades de mensajes entrantes** propiedad está seleccionada en la entidad como página del remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en el [!INCLUDE[prague](../includes/prague-md.md)] consola de administración, el **de mensajes debe estar firmado** propiedad está seleccionada, pero el mensaje no está firmado, póngase en contacto con la entidad que envió el mensaje y pídale que firme el mensaje y lo vuelva a enviar. También puede desactivar la **debe firmarse el mensaje** propiedad, o la **invalidar propiedades de mensajes entrantes** propiedad.  
  
2.  Si el **invalidar propiedades de mensajes entrantes** propiedad está seleccionada, el **debe firmarse el mensaje** propiedad está desactivada, pero el mensaje está firmado, póngase en contacto con la entidad que envió el mensaje y pídale que no firmar el mensaje y lo vuelva a enviar. O bien puede seleccionar la **debe firmarse el mensaje** propiedad.
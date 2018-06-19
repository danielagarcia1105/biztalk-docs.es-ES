---
title: Error de configuración. El no cifrado de mensaje &#39; t coincide con el valor esperado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4920a4c26cb60c3215f58297445dc49551b1befe
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004790"
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a>Error de configuración. El no cifrado de mensaje &#39; coincidencia t el valor esperado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2DecoderPartyEncryptionConfigurationError|  
|Texto del mensaje|Error de configuración. El cifrado del mensaje no coincide con el valor esperado. Póngase en contacto con el socio remitente y verifique el uso del cifrado. AS2-de: "{0}" AS2-para: "\ {1\\}" MessageID: "\ {2\}"|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el componente de descodificador AS2 de la canalización de recepción no pudo procesar el mensaje AS2 porque el cifrado está especificado en la configuración de la entidad y el mensaje AS2 no está cifrado, o bien el cifrado está especificado para que no se habilite, pero el mensaje está cifrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe que el mensaje AS2 entrante está cifrado si el cifrado está especificado en la configuración de la entidad o bien que el mensaje AS2 entrante no está cifrado si el cifrado está especificado como no habilitada en la configuración de la entidad. Realice una de las siguientes operaciones:  
  
1.  Si el **invalidación está seleccionada la propiedad de propiedades de mensaje entrante** en la página entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2 en la consola de administración de BizTalk Server, el **debe cifrarse el mensaje**  propiedad está seleccionada, pero no se cifra el mensaje, póngase en contacto con la entidad que envió el mensaje y pídale que cifre el mensaje y lo vuelva a enviar. También puede desactivar la **debe cifrarse el mensaje** propiedad, o la **invalidar propiedades de mensajes entrantes** propiedad.  
  
2.  Si el **invalidar propiedades de mensajes entrantes** propiedad está seleccionada, el **debe cifrarse el mensaje** propiedad está desactivada, pero el mensaje está cifrado, póngase en contacto con la entidad que envió el mensaje y pídale que No cifrar el mensaje y lo vuelva a enviar. O bien puede seleccionar la **debe cifrarse el mensaje** propiedad.
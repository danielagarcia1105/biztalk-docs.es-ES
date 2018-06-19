---
title: Resolución del acuerdo para mensajes AS2 salientes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cf35a15ca7d0e27ba0c2bf1a05781d6512e0bef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230324"
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a>Resolución del acuerdo para mensajes AS2 salientes
Si una canalización de envío AS2 procesa un mensaje codificado con EDIINT/AS2 saliente a través del transporte HTTP/HTTPS, determina el acuerdo que resolverá el mensaje. Utilizará dichas propiedades de acuerdo para procesar el mensaje saliente. La canalización de envío usará los siguientes criterios para determinar el acuerdo (en orden de prioridad):  
  
1.  La canalización de envío intenta establecer una correspondencia entre las propiedades AS2From y AS2To del contexto y los valores de AS2From y AS2To especificados como parte de las propiedades del acuerdo.  
  
2.  Si se produce un error en el paso anterior, la canalización de envío intentará hacer coincidir la propiedad de contexto AS2To del mensaje saliente con el valor de la propiedad AS2To, que se ha establecido como resolución de acuerdo adicional en el **identificadores** ficha del acuerdo Propiedades.  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no escribe la propiedad AS2To en el contexto. Si desea realizar la resolución del acuerdo en la propiedad de contexto AS2To, deberá incorporar una orquestación personalizada o un componente de canalización personalizado para ello. Para obtener más información, consulte [propiedades de contexto de AS2 de escritura para la resolución de entidades salientes](../core/writing-as2-context-properties-for-outbound-party-resolution.md).  
  
    > [!NOTE]
    >  Si está utilizando un puerto de envío dinámico, la propiedad AS2To se debe escribir en el contexto de la resolución del acuerdo.  
  
3.  Si se produce un error en el paso anterior, la canalización de envío tratará de establecer una correspondencia entre el puerto de envío asociado al acuerdo y el puerto de envío que se ha suscrito al mensaje. El puerto de envío está asociado con el acuerdo en el **puertos de envío** página del acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo.  
  
    > [!NOTE]
    >  A diferencia del procesamiento EDI, no existen propiedades AS2 de reserva que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda usar en caso de que no pueda determinar el acuerdo. Sin embargo, hay un acuerdo predeterminado que se usa para enviar un MDN. Además, ni el puerto de envío ni la propiedad de contexto Http.UserHttpHeaders se usan para resolver el acuerdo de un MDN. Para obtener más información, vea la sección "Acuerdo resolución para un MDN" de [enviar un MDN saliente](../core/sending-an-outgoing-mdn.md).  
  
    > [!NOTE]
    >  Si AS2-a propiedades de acuerdo en el **identificadores** página del acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo se establece de forma predeterminada para un nombre de entidad en inglés y el valor de AS2-al encabezado de AS2 mensajes se establece en un nombre no está en inglés, a continuación, no se encontrará la coincidencia.  
  
> [!NOTE]
>  Al enviar EDI sobre AS2, es necesario utilizar acuerdos independientes para EDI y AS2.  
  
 Para obtener más detalles sobre el proceso de envío, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)
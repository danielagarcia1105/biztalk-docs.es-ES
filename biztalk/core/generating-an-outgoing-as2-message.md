---
title: Generar un mensaje AS2 saliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246548"
---
# <a name="generating-an-outgoing-as2-message"></a>Generar un mensaje AS2 saliente
Las canalizaciones de envío AS2EDISend y AS2Send generan un mensaje saliente como se explica a continuación. Cada canalización utiliza las propiedades en la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo para generar el mensaje AS2 saliente.  
  
## <a name="agreement-destination-and-messageid-determination"></a>Determinación del acuerdo, el destino y el identificador de mensaje  
 Las canalizaciones de envío de AS2 determinan el acuerdo y el destino que van a usarse en el envío del mensaje AS2 de la siguiente forma:  
  
-   Para determinar qué acuerdo se debe usar en el procesamiento de un mensaje saliente, el codificador AS2 intenta hacer coincidir las propiedades AS2-To del mensaje y la AS2Identity del perfil de negocio de una entidad, o el puerto de envío de suscripción al mensaje con un puerto de envío asociado al acuerdo. Para obtener más información acerca de este proceso, consulte [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).  
  
-   Para determinar el destino del mensaje, la canalización de envío de un puerto de envío dinámico usa la propiedad OutboundTransportLocation, que debe estar escrita o promocionada al contexto mediante una aplicación de servidor para que funcione el puerto de envío dinámico. La canalización de envío de una canalización de envío estático determinará el destino a partir de la propiedad AS2-From de las propiedades del acuerdo AS2 y de las identidades de las propiedades del perfil de negocio.  
  
-   El codificador AS2 debe establecer el encabezado MessageId de un mensaje AS2 saliente. La canalización de envío determina el identificador de mensaje a partir de la propiedad de contexto `EdiIntAS.MessageId` o la propiedad de contexto `HTTP.UserHttpHeaders`. Si ambas propiedades de contexto están establecidas, el codificador usa el valor de la propiedad de contexto `HTTP.UserHttpHeaders`. Si ninguna está establecida, la canalización de envío genera de forma automática un valor para MessageID.  
  
## <a name="outgoing-message-processing"></a>Procesamiento de mensajes salientes  
 Los pasos que usa una canalización de envío de AS2 en el procesamiento de un mensaje saliente de AS2 son los siguientes:  
  
-   Realiza una copia del mensaje en formato nativo y almacena la copia en la base de datos sin repudio, si la recepción sin repudio de mensajes AS2 está habilitada en las propiedades del acuerdo.  
  
-   El codificador AS2 genera los encabezados HTTP (y AS2) en la propiedad de contexto `HTTP.UserHttpHeaders`. Para obtener más información acerca de este proceso, consulte [envíos de procesamiento de un mensaje EDI saliente a través de AS2](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md).  
  
-   Escribe `HTTP.UserHttpHeaders` en el contexto.  
  
-   Comprime el mensaje saliente, si esta opción está habilitada.  
  
-   Realiza un procesamiento MIME, incluido el cifrado del mensaje (si se habilita en el **debe cifrarse el mensaje** propiedad de acuerdo) y aplicar una firma digital (si habilitada en el **de mensajes debe estar firmado**propiedades de acuerdo). La canalización AS2Send usa SHA1 o MD5 para aplicar la firma, en función de la configuración del acuerdo.  
  
-   Crea un encabezado MIME Content-Disposition que contiene el valor especificado, si está activada la transmisión del nombre de archivo en las propiedades del acuerdo.  
  
-   Realiza una copia del mensaje cifrado (en su formato correspondiente) y almacena la copia en la base de datos sin repudio, si se habilita en el **NRR habilitado para mensajes AS2 salientes codificados** en la propiedad de acuerdo.  
  
-   Si se requiere un MDN, calcula el valor MIC y lo guarda en el almacén de datos.  
  
-   Entrega el mensaje al adaptador de HTTP, que escribe los encabezados de la propiedad de contexto UserHTTPHeaders en el mensaje AS2 saliente.  
  
-   Si se requiere la mensajería de confianza, reenvía el mensaje hasta que se reciba un MDN.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes AS2](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 Componentes de envío](../core/as2-send-components.md)
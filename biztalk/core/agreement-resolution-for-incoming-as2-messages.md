---
title: Resolución del acuerdo para mensajes AS2 entrantes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e5e9795979ddf0a8b8f13fe7ab53bd4e783bd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230156"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a>Resolución del acuerdo para mensajes AS2 entrantes
Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje con codificación EDIINT/AS2 sobre el transporte HTTP/HTTPS, intenta determinar el perfil de negocio del socio comercial que envió el mensaje. Para ello, trata de realizar lo que se indica a continuación (en el mismo orden que se muestra):  
  
1.  Establece una correspondencia entre AS2-del encabezado del mensaje entrante con el valor de **AS2-de** en el **identificadores** página del acuerdo AS2 unidireccional en la **propiedades del acuerdo de** cuadro de diálogo.  
  
2.  Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo, intentará corresponder la propiedad de contexto AS2-From que se haya establecido para el mensaje entrante con el nombre de un socio comercial.  
  
> [!NOTE]
>  Puesto que el encabezado AS2-From solo puede contener caracteres ASCII, debe asegurarse de que el nombre del socio comercial y el alias AS2-From contienen únicamente caracteres ASCII. Si no se encuentra una coincidencia exacta, BizTalk no podrá determinar el acuerdo basándose en los encabezados de mensaje entrante.  
  
 La canalización de recepción AS2 solo procesará el mensaje si se ha determinado un acuerdo. A diferencia del procesamiento EDI, no existen propiedades AS2 de reserva que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda usar en caso de que no pueda determinar el acuerdo.  
  
 Una vez que la canalización haya determinado el acuerdo, comprobará la configuración de la **usan acuerdo de encabezado del mensaje de configuración para la validación y MDN en su lugar** propiedad en el **validación** página de AS2 unidireccional acuerdo en el **la configuración de acuerdo** cuadro de diálogo. Si está activada esa propiedad, la canalización de recepción usará las propiedades de acuerdo para procesar el mensaje. Si la propiedad está desactivada, la canalización de recepción usará los valores del encabezado de AS2 del mensaje para llevar a cabo el procesamiento.  
  
> [!NOTE]
>  Es posible que el acuerdo AS2 que se determina durante la resolución de acuerdo no sea el mismo que la carga EDI. No hay ningún requisito que indique que AS2 y EDI deben compartir el mismo acuerdo, ya que el acuerdo AS2 puede representar una cámara de compensación que enruta documentos EDI de varias entidades.  
  
 Para obtener más detalles sobre el proceso de recepción, consulte [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server recibe mensajes AS2](../core/how-biztalk-server-receives-as2-messages.md)
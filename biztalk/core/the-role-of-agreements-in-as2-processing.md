---
title: Rol de los acuerdos AS2 procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb6a6fe1-8fb4-4998-a1b4-aadad7e672c4
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 712c086cd02eedfd1995e5f378a05d2edd34bb6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-role-of-agreements-in-as2-processing"></a>Rol de los acuerdos en el procesamiento de AS2
Una organización usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes AS2 de uno o varios socios comerciales, así como para enviar mensajes AS2 a ellos. A su vez, los socios comerciales definen perfiles de negocio que son entidades de negocio dentro de una organización. Las propiedades de AS2 se establecen en acuerdos entre socios comerciales bidireccionales entre dos perfiles de negocio que pertenecen a socios comerciales distintos.  
  
 Los acuerdos entre socios comerciales se pueden crean en la interfaz de usuario de administración de socios comerciales (TPM). Las pantallas TPM se encuentran en el **partes** nodo de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 Para obtener más información acerca de cómo socios, perfiles de negocio y acuerdos en una solución TPM, consulte [bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md).  
  
## <a name="configuring-an-agreement-for-as2-processing"></a>Configuración de un acuerdo para el procesamiento de AS2  
 Cuando un socio comercial recibe un mensaje AS2 procedente de otro socio comercial, o le envía un mensaje AS2, la canalización de recepción AS2 o la canalización de envío AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesará el mensaje en función de las propiedades del acuerdo AS2 entre los dos socios comerciales. Puede configurar las propiedades de AS2 que definen el modo en que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizará las comunicaciones de AS2, tanto las entrantes como las salientes.  
  
> [!NOTE]
>  A diferencia del procesamiento EDI, no existen acuerdos AS2 de reserva que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda usar en caso de que no pueda determinar el acuerdo. La canalización de recepción o de envío AS2 solo procesará el mensaje si se ha determinado un acuerdo.  
  
> [!NOTE]
>  El acuerdo AS2 se configura de forma independiente al acuerdo EDI. Cuando se reciben documentos, el acuerdo AS2 se resuelve durante el procesamiento AS2; a continuación, el acuerdo EDI se resuelve de forma independiente durante el procesamiento EDI. Los dos acuerdos juntos forman una asociación. Para obtener más información, consulte [acuerdo de socios comerciales](../core/trading-partner-agreement.md).  
  
> [!NOTE]
>  Las propiedades que definen aspectos generales de la entidad, como el nombre y los alias, los puertos de envío y el certificado de firma se especifican como parte de las propiedades del socio comercial.  
  
 Puede usar el transporte HTTP/HTTPS para mensajes con codificación EDIINT y AS2 o mensajes no EDI sobre codificación AS2. Si transmite mensajes con codificación EDIINT/AS2 a través de transporte HTTP/HTTPS, se aplicarán las propiedades de EDI para el acuerdo.  
  
 El certificado de firma de la organización propia se define en el **certificado** página de la **grupo de BizTalk - propiedades de grupo** cuadro de diálogo. Asimismo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite invalidar el certificado de firma predeterminado para mensajes AS2 mediante la definición de un certificado como parte de las propiedades del acuerdo.  Para definir un certificado diferente para un acuerdo específico, use el **certificado de firma** página del acuerdo AS2 unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Para obtener instrucciones sobre cómo especificar un certificado diferente, consulte [configurar certificados de firma (AS2)](../core/configuring-signature-certificates-as2.md).  
  
## <a name="determining-an-agreement-for-as2-processing"></a>Determinación de un acuerdo para el procesamiento de AS2  
 Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje con codificación AS2, intenta determinar qué entidad ha enviado el mensaje mediante la correspondencia entre el encabezado AS2-From y la configuración de acuerdo AS2-From del acuerdo unidireccional para la entidad. Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía un mensaje con codificación AS2, intenta determinar qué entidad recibirá el mensaje mediante la correspondencia entre el encabezado AS2-To y la propiedad de acuerdo AS2-To del acuerdo unidireccional para la entidad. Para obtener más información, consulte [resolución del acuerdo para mensajes AS2 entrantes](../core/agreement-resolution-for-incoming-as2-messages.md) o [resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md).  
  
## <a name="see-also"></a>Vea también  
 [Resolución del acuerdo para mensajes AS2 entrantes](../core/agreement-resolution-for-incoming-as2-messages.md)   
 [Resolución del acuerdo para mensajes AS2 salientes](../core/agreement-resolution-for-outgoing-as2-messages.md)   
 [Configurar propiedades de AS2](../core/configuring-as2-properties.md)
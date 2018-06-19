---
title: Perfiles de negocio y socios comerciales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbeac421-c319-4a60-a188-28f7268888fc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fff632199d3acd8be4ade7724eaa49748dab5db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279540"
---
# <a name="trading-partners-and-business-profiles"></a>Perfiles de negocio y socios comerciales

## <a name="overview"></a>Información general
Cada organización participante en una relación de negocio es un socio comercial. Los socios comerciales, llamados también “entidades comerciales” o “entidades”, se encuentran en el nivel raíz y forman la base de una solución de socios comerciales. Un socio comercial es uno de los dos o más participantes en una relación de negocio en curso. Un socio comercial es cualquier entidad de negocio individual que puede enviar mensajes a otros socios y recibir mensajes de ellos.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], solución TPM se puede usar para modelar y almacenar información de cualquier socio comercial, como enviar los puertos asociaciones y certificados que se usan para validar la identidad de una entidad. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]usa esta información para controlar los mensajes recibidos y los mensajes enviados. Cada organización participante en una relación de negocios, incluida la organización interna (la organización de host local que se ejecuta el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host), se representa como un socio comercial.
  
 ![Entidades comerciales](../core/media/tradingparties.gif "TradingParties")  
  
 Por ejemplo, considere dos organizaciones: Fabrikam y Contoso. Fabrikam utiliza [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar todos los intercambios de datos de negocio con Contoso, Fabrikam debe crear dos socios comerciales, uno propio y otro para Contoso. Al crear una entidad, proporcionar determinados detalles como el asociado de nombre y así sucesivamente.  
 
## <a name="business-profiles"></a>Perfiles de negocio

Un perfil de negocio de un socio comercial, denominado también perfil de negocio, es la faceta de negocios de una organización. Cada división de negocios de una organización que comercia con otra división de negocios de otra organización se representa como perfil de negocio en una solución TPM. Todas las propiedades que definen los parámetros de mensajería B2B específicos de la división, la unidad o el sistema de negocio se capturan en el perfil de negocio. Por ejemplo, supongamos que Fabrikam tienen dos divisiones de negocio: "Pago" y "Shipping". Contoso tiene una división de negocio "Facturas". Teniendo en cuenta Fabrikam usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe crear:  
  
-   Dos perfiles de negocio, uno para Pago y otro para Envío, bajo el socio comercial Fabrikam.  
  
-   Un perfil de negocio para Factura, bajo el socio comercial Contoso.  
  
 En la ilustración siguiente se muestra cómo los perfiles de negocio y de socios comerciales se administran en una solución TPM:  
  
 ![Perfiles de socios de socios comerciales](../core/media/businessprofile.gif "BusinessProfile")  
  
 Una vez definidos los perfiles de negocio, las divisiones de negocio pueden definir los formatos de codificación de mensajes y los transportes a los que las divisiones de negocio se adhieren durante el envío y la recepción de mensajes B2B. Estos patrones de comunicación entre los perfiles de negocio se tratan en [configuración del protocolo](../core/protocol-settings.md).  
  
### <a name="why-do-i-need-business-profiles"></a>¿Por qué necesito perfiles de negocio?  
 Los perfiles de negocio permiten que los usuarios de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] representen mejor su modelo de negocios en una solución TPM. Una empresa con múltiples divisiones de negocio puede representarse por separado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Y lo que es más importante, este modelo permite a los usuarios definir propiedades para cada perfil de negocio, que definen cómo ese perfil realiza sus transacciones con otros perfiles. Por ejemplo, considere una empresa que tenga divisiones en Estados Unidos y Europa. La división de Estados Unidos espera mensajes EDI únicamente en X12 estándar, mientras que la división en Europa espera mensajes EDI únicamente en EDIFACT estándar. Mediante la creación de entidades, la empresa puede establecer el derecho de las propiedades de mensajería en el nivel de perfil y al mismo tiempo utilizan las propiedades que ya están establecidas en el nivel de socio comercial. Sin perfiles de negocio, la empresa tendría que crear a socios comerciales para todas las divisiones de negocio y, a continuación, replicar un host de propiedades a través de los socios comerciales.  
  
 También puede asociar las identidades de negocio con perfiles de negocio para que tengan una identificación única. Estas identidades de negocio pueden ser proporcionadas por un cuerpo estándar o pueden ser un acuerdo mutuo, en función de la identidad de negocio.  
  
> [!IMPORTANT]
>  Si dos divisiones de negocio de la misma organización necesitan realizar transacciones entre ellas, deben crearse como socios comerciales separados. Dos perfiles bajo el mismo socio comercial no pueden realizar transacciones entre ellos, ya que las relaciones de socios comerciales únicamente se administran entre socios comerciales distintos.  
  
## <a name="learn-next"></a>Obtenga información acerca de continuación

[Configuración del protocolo](../core/protocol-settings.md)  
[Acuerdo de socio comercial](../core/trading-partner-agreement.md)  
[Perspectiva general: definir una solución de administración de socios comerciales](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
 
## <a name="see-also"></a>Vea también  
 [Bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md)
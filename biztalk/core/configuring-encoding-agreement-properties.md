---
title: Configurar las propiedades del acuerdo de codificación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.ediagreement.properties
ms.assetid: 0cb1146e-177c-42fa-b1d8-a834229c2af9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0323bde34a7ef9abcbba15d8dd8059fee0c51c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012013"
---
# <a name="configuring-encoding-agreement-properties"></a>Configuración de propiedades del acuerdo de codificación
Un acuerdo de socios comerciales (TPA) es un acuerdo vinculante y definitivo entre dos socios comerciales para la transacción de mensajes a través de un protocolo B2B específico. En términos más sencillos, un TPA es un acuerdo entre dos perfiles empresariales para usar un protocolo específico de codificación de mensajes (X12 o EDIFACT) o un protocolo específico de transporte (AS2) al intercambiar mensajes B2B entre sí. Además de acordar el protocolo de codificación y transporte, se puede usar un acuerdo para personalizar el modo en que se forman y entregan los mensajes.  
  
- Como parte de la configuración del protocolo de codificación, también puede definir si la entidad que envía espera una confirmación, si los mensajes se enviarán por lotes o individualmente, etc.  
  
- Como parte de la configuración del protocolo de transporte, también puede definir si debe firmarse, cifrarse, etc. el mensaje.  
  
  > [!NOTE]
  >  Para obtener más información acerca de la configuración de transporte Protocolo (AS2), consulte [configurar propiedades del acuerdo AS2](../core/configuring-as2-agreement-properties.md).  
  
  Debe tener en cuenta las siguientes consideraciones al crear un acuerdo:  
  
- Un acuerdo de socio comercial entre dos entidades es bidireccional. Un acuerdo único entre dos entidades (la Entidad A y la Entidad B) se puede usar para enviar mensajes desde la Entidad A a la Entidad B y también para recibir mensajes de la Entidad B a la Entidad A. Para representar un acuerdo bidireccional en la interfaz de usuario, cada acuerdo unidireccional se representa en una única pestaña. Por lo tanto, en la interfaz de usuario de acuerdo, verá dos fichas, **entidad a -> PartyB** (que representa el acuerdo unidireccional para los mensajes enviados desde la entidad A la entidad B) y **PartyB -> entidad a** (que representa el acuerdo unidireccional para los mensajes enviados desde la entidad b a la entidad a.)  
  
- Cada acuerdo unidireccional se encarga de la transacción de mensaje de un extremo a otro. Enviar o recibir confirmaciones también forma parte de la misma transacción de mensaje, por lo que debe configurarse en la misma pestaña del acuerdo unidireccional. Por ejemplo, considere la posibilidad de envíos de entidad de un intercambio EDI a la entidad B y en respuesta, entidad B envía una confirmación a la entidad A. Por lo tanto, se deben establecer todas las propiedades relacionadas para enviar un intercambio y espera una confirmación en el **entidad a -> PartyB** ficha.  
  
  > [!NOTE]
  >  Aunque la confirmación es parte de la misma transacción de mensaje, se configuran las propiedades relacionadas con el modo en que debe generarse la confirmación en el **PartyB -> entidad a** ficha. Esto es necesario porque las propiedades de contexto de confirmación para el remitente y receptor calificadores se establecen en el efecto contrario de los valores especificados en el **entidad a -> PartyB** ficha. Por ejemplo, si los identificadores del remitente y el destinatario se configuran en ELLOS y NOSOTROS en el acuerdo en el cual se resuelve el mensaje de intercambio, las propiedades de contexto del remitente y el destinatario se configurarán en NOSOTROS y ELLOS en la confirmación. Normalmente, la otra ficha de acuerdo unidireccional también tendrá los identificadores de remitente y receptor configurados respectivamente en NOSOTROS y ELLOS. Por lo tanto, el mensaje de confirmación se resolverá en dicho acuerdo y se seleccionará la configuración de propiedades. Por lo tanto, si desea tener confirmación para usar diferentes separadores de elementos o si desea tener confirmación para usar CR LF, especifique las propiedades en el **PartyB -> entidad a** ficha.  
  >   
  >  Conceptualmente, las propiedades para la confirmación se seleccionarán desde cualquier ficha de acuerdo unidireccional que tenga los mismos calificadores de remitente y receptor que están configurados en las propiedades de contexto de la confirmación. No obstante, para facilitar su uso en la práctica, normalmente debe configurar esto en la otra ficha de acuerdo unidireccional del acuerdo que creó en el cual debe haberse resuelto el intercambio.  
  
- Puede tener un acuerdo de codificación (para definir la codificación de mensajes que debe usarse para los mensajes) y un acuerdo de transporte (para definir el protocolo de transporte que debe usarse para intercambiar mensajes). Es obligatorio disponer de un acuerdo de codificación. Las entidades pueden elegir tener un acuerdo AS2 solo si desean usarlo para transferir mensajes. Por ejemplo, un acuerdo AS2 no es obligatorio si las dos partes deciden transferir mensajes a través del correo electrónico.  
  
  > [!NOTE]
  >  Para obtener más información acerca del acuerdo AS2, vea [configurar propiedades del acuerdo AS2](../core/configuring-as2-agreement-properties.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de las propiedades de acuerdos específicos de X12](../core/configuring-x12-specific-agreement-properties.md)  
  
-   [Configuración de las propiedades de acuerdos específicos de EDIFACT](../core/configuring-edifact-specific-agreement-properties.md)
---
title: Configuración del protocolo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 224a9837-5c85-4511-b6d9-c8fda63a27d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5d32f7a691aa9781760f0d7711d7f20851a038
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989285"
---
# <a name="protocol-settings"></a>Configuración de protocolo
## <a name="overview"></a>Información general
Después de crear los perfiles de negocio, que reflejan las divisiones de la empresa dentro de una organización, es necesario que una empresa declare los parámetros que definen cómo tiene lugar la comunicación entre los perfiles de negocio. Estos parámetros de comunicación se definen como configuración del protocolo. La configuración del protocolo define cómo deben admitirse las transacciones empresariales para un determinado protocolo B2B. Cada perfil de negocio define las diversas opciones para procesar mensajes (codificación) o transmitir mensajes (transporte) para cada uno de los protocolos B2B a través de los cuales puede comunicarse el socio. Los parámetros de comunicación para los perfiles de negocio se definen en las dos categorías siguientes:  
  
- **Configuración de protocolo de codificación**: los protocolos de codificación rigen la estructura y el contenido de un mensaje de B2B. La configuración del protocolo de codificación para un perfil de negocio define el protocolo de codificación que usa una división empresarial para enviar y recibir mensajes B2B. Algunos ejemplos de protocolos de codificación son X12, EDIFACT, HL7, etcetera. Para obtener una explicación detallada aproximadamente admite protocolos de codificación para [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], consulte [compatibilidad con estándares EDI](../core/edi-standards-support.md). Como parte del protocolo de codificación, puede proporcionar varias opciones, como si la parte que envía espera una confirmación, si los mensajes se enviarán por lotes o individualmente, etc. Siempre podrá sobrescribir estas opciones como parte del acuerdo de socio comercial. Consulte [acuerdo entre socios comerciales](../core/trading-partner-agreement.md).  
  
- **Configuración del protocolo de transporte**: el protocolo de transporte rige el canal de transporte usado para enviar los mensajes entre dos socios. Dado que el transporte es esencialmente entre dos extremos de transporte, cada perfil de negocio define su propia configuración de “extremo de transporte” y se comunica con un “extremo de transporte” singular del perfil de negocio de su socio comercial. Para obtener información acerca del protocolo de transporte admitidos, vea [compatibilidad con AS2 en BizTalk Server](../core/as2-support-in-biztalk-server.md). Como parte del protocolo de transporte, puede proporcionar varias opciones, como si debe firmarse, cifrarse, etc. el mensaje. Siempre podrá sobrescribir estas opciones como parte del acuerdo de socio comercial. Para obtener más información acerca de los acuerdos, vea [acuerdo entre socios comerciales](../core/trading-partner-agreement.md).  
  
  Mediante la definición de la configuración del protocolo, los perfiles de negocio declaran el formato de mensaje y el protocolo de transporte que debe usarse para enviar mensajes B2B entre socios comerciales.  
  
> [!NOTE]
>  Definir la configuración de protocolo como parte de un perfil de negocio es opcional. Si no especifica la configuración de protocolo como parte del perfil de negocio, siempre puede especificarlo en un acuerdo.  
  
 En la siguiente figura se ilustra cómo se reúnen socio comercial, perfiles de negocio y configuración de protocolo en una solución TPM:  
  
 ![Perfiles de socios comerciales y la configuración del protocolo comerciales](../core/media/protocolsettings.gif "ProtocolSettings")  
  
 En la ilustración anterior, el perfil de negocio “Shipping” puede enviar y recibir mensajes con el formato de codificación X12 enviado sobre el protocolo de transporte AS2. De forma similar, el perfil de negocio “Invoice” puede enviar y recibir mensajes de los formatos de codificación tanto X12 como EDIFACT sobre el protocolo de transporte AS2.  
  
 Ahora resulta evidente de qué modo puede ayudar la definición de un perfil de negocio para crear una solución TPM en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En la actualidad, como muestra la ilustración, el perfil de negocio “Shipping” solo puede enviar y recibir mensajes X12. Por lo tanto, cualquier perfil de negocio que se comunique con el perfil de negocio “Shipping” deberá adherirse a su configuración de propiedades. No obstante, en el futuro, si el perfil de negocio “Shipping” comienza a aceptar mensajes con la codificación EDIFACT, solo tiene que establecer las propiedades relevantes para incluir la compatibilidad con EDIFACT. La organización del socio no tiene que crear un nuevo perfil de negocio para la misma división de envío.  
  
## <a name="do-i-always-need-to-specify-the-protocol-settings-when-creating-a-business-profile"></a>¿Es siempre necesario especificar la configuración del protocolo al crear un perfil de negocio?  
 Teóricamente, sí: un perfil de negocio debe contener la definición de configuración de protocolo. Sin embargo, esto no implica que deba definir la configuración de protocolo al crear un perfil de negocio en la interfaz de usuario de TPM. TPM le proporciona flexibilidad para que pueda especificar la configuración del protocolo mientras crear el perfil de negocio o mientras crea un acuerdo de socio comercial. Si define la configuración del protocolo como parte del perfil de negocio, estará disponible mientras crea un acuerdo de socio comercial para dicho perfil. No obstante, si define la configuración del protocolo como parte del acuerdo, deberá proporcionar todos los valores como parte del acuerdo.  
  
> [!IMPORTANT]
>  Si no define la configuración del protocolo como parte del perfil de negocio, deberá especificar los valores como parte de cada acuerdo para dicho perfil de negocio, evitando así el modelo de escalabilidad de la nueva solución de TPM. Por lo tanto, Microsoft recomienda que defina la configuración del protocolo para cada perfil de negocio. Siempre podrá anular dicha configuración si es necesario, al crear un acuerdo de socio comercial.  

## <a name="learn-next"></a>Aprenda a continuación
[Acuerdo entre socios comerciales](../core/trading-partner-agreement.md)  
[Perspectiva general: Definición de una solución de administración de socios comerciales](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)  
  
## <a name="see-also"></a>Vea también  
 [Bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md)
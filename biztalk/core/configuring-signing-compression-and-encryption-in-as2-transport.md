---
title: Configuración de firma, compresión y cifrado en el transporte AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc3537a7-c065-4a33-a375-29e7902b5ffa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a154255cb64fcebafa2ef8164714e46bf5673ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007207"
---
# <a name="configuring-signing-compression-and-encryption-in-as2-transport"></a>Configurar la firma, la compresión y el cifrado en el transporte AS2
Puede configurar las firmas digitales, así como la verificación, el cifrado y el descifrado de firmas desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para llevar a cabo esta configuración, es preciso establecer las propiedades adecuadas para las canalizaciones AS2 y las entidades de BizTalk.  
  
## <a name="using-as2-pipelines"></a>Usar canalizaciones AS2  
 Para contribuir a proteger un mensaje AS2 entrante, use una canalización de recepción AS2 (AS2EdiReceive o AS2Receive) en la ubicación de recepción. El descodificador AS2 descifra, descomprime y realiza la verificación de la firma en mensajes AS2. Para obtener más información sobre cómo lo hace, vea la sección "Descodificador AS2" de [componentes de recepción AS2](../core/as2-receive-components.md).  
  
 Para contribuir a proteger un mensaje AS2 saliente, use una canalización de envío AS2 (AS2EdiSend o AS2Send) en el puerto de envío. El descodificador AS2 firma, comprime y cifra los mensajes AS2 salientes. Para obtener más información sobre cómo lo hace, vea la sección "Codificador AS2" de [componentes de envío AS2](../core/as2-send-components.md).  
  
> [!IMPORTANT]
>  Una vez que se ha firmado un mensaje, el blob de firma no se debe cambiar. De hacerlo, la firma se dañaría. El encabezado de límite, o cualquier elemento fuera de los encabezados de límite, puede modificarse, pero no se debe cambiar nada que se encuentre dentro de estos encabezados.  
  
## <a name="setting-as2-agreement-properties"></a>Configuración de las propiedades del acuerdo AS2  
 Para configurar el procesamiento de firmas y el cifrado puede establecer las propiedades del acuerdo AS2 de la manera siguiente:  
  
- Para firmar, comprimir o cifrar un mensaje saliente, compruebe el **debe firmarse el mensaje**, **debe comprimirse el mensaje**, y **debe cifrarse el mensaje** las propiedades de la **validación** página de la ficha de acuerdo unidireccional (para el mensaje AS2 saliente) en el **las propiedades del acuerdo** cuadro de diálogo.  
  
- Para solicitar un MDN firmado en respuesta a un mensaje saliente, compruebe el **solicitar MDN** y **solicitar MDN firmada** propiedades en el **confirmaciones (MDN)** página de la ficha de acuerdo unidireccional del **las propiedades del acuerdo** cuadro de diálogo.  
  
- Para especificar que un mensaje entrante está firmado, comprimido, o cifrado, compruebe el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad, el **debe firmarse el mensaje** propiedad, el **debe comprimirse el mensaje** propiedad y el **debe cifrarse el mensaje** propiedad en el **validación** página del acuerdo unidireccional la pestaña (para el mensaje AS2 entrante) en el **las propiedades del acuerdo** cuadro de diálogo.  
  
  > [!NOTE]
  >  Cuando el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada, se omiten todos los detalles del encabezado del mensaje entrante y el mensaje se procesa en función de la configuración del acuerdo.  
  
- Para especificar un MDN firmado en respuesta a un mensaje entrante, cuando se invalidan las propiedades de mensajes entrantes seleccionando la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad, compruebe el **Solicitar MDN firmado** propiedad **confirmaciones (MDN)** página de la **las propiedades del acuerdo** cuadro de diálogo.  
  
  > [!NOTE]
  >  Cuando el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada, se omiten todos los detalles del encabezado del mensaje entrante y el mensaje se procesa en función de la configuración del acuerdo.  
  
- Para especificar un MDN firmado en respuesta a un mensaje entrante, cuando no se invalidan las propiedades del mensaje entrante (el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** está desactivada), pero no los encabezados del mensaje especificar la firma, compruebe el **firmar el MDN solicitado si el encabezado Disposition-Notification-Option no está presente o si el encabezado Signed-Receipt-Protocol está establecido en opcional** propiedad en el **configuración de MDN de receptor**página de la **las propiedades del acuerdo** cuadro de diálogo.  
  
- Para especificar un certificado de firma diferente a la especificada en las propiedades del grupo de BizTalk para mensajes AS2 salientes, seleccione **invalidar certificado de firma de grupo** en el **certificado de firma**página de la ficha de acuerdo unidireccional de la **las propiedades del acuerdo** diálogo cuadro y especifique un certificado de firma. Si se establece esta propiedad, el mensaje AS2 que se resuelve en el acuerdo estará firmado con el certificado proporcionado en el **certificado de firma** página y no por el certificado proporcionado como parte de las propiedades del grupo de BizTalk.  
  
  Para obtener más información acerca de cómo configurar las propiedades de entidad, vea [configurar propiedades de AS2](../core/configuring-as2-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de AS2](../core/as2-security.md)   
 [Configurar certificados para AS2](../core/configuring-certificates-for-as2.md)   
 [Mensajes AS2](../core/as2-messages.md)   
 [AS2 Componentes de recepción](../core/as2-receive-components.md)   
 [AS2 Componentes de envío](../core/as2-send-components.md)   
 [Configuración de las propiedades AS2](../core/configuring-as2-properties.md)
---
title: Configurar las propiedades del acuerdo de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.as2agreement.properties
ms.assetid: a62d8d2a-0b8d-4179-a48f-92f135b5787d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 960397bdce5090f57b9f2fe6882a27d313631df6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000837"
---
# <a name="configuring-as2-agreement-properties"></a>Configuración de las propiedades de acuerdo AS2
Esta sección describe las propiedades de acuerdo de transporte AS2. Como parte de la configuración del protocolo de transporte, también puede definir si debe firmarse, cifrarse, etc. el mensaje.  
  
> [!NOTE]
>  La configuración de un acuerdo AS2 es opcional. Un acuerdo AS2 define cómo se transfieren los mensajes mediante el protocolo AS2. Si los socios comerciales deciden usar cualquier otro protocolo de transporte para transferir mensajes, pueden elegir no definir un acuerdo AS2. Sin embargo, los socios comerciales deben definir un acuerdo de codificación que rija cómo se forman y codifican los mensajes. Para obtener más información acerca de los acuerdos de codificación, vea [configurar propiedades del acuerdo de codificación](../core/configuring-encoding-agreement-properties.md).  
> 
> [!IMPORTANT]
>  Cada vez que modifique una configuración AS2 en un acuerdo, deberá reiniciar la instancia host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que los cambios surtan efecto.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración general (AS2)](../core/configuring-general-settings-as2.md)  
  
-   [Configuración de identificadores (AS2)](../core/configuring-identifiers-as2.md)  
  
-   [Configuración de la validación (AS2)](../core/configuring-validation-as2.md)  
  
-   [Configuración de confirmaciones (MDN) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)  
  
-   [Configuración de las opciones de host local (AS2)](../core/configuring-local-host-settings-as2.md)  
  
-   [Configuración de certificados de firma (AS2)](../core/configuring-signature-certificates-as2.md)  
  
-   [Configuración de la asociación de puertos de envío (AS2)](../core/configuring-send-port-association-as2.md)  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades AS2](../core/configuring-as2-properties.md)
---
title: Configuración de identificadores (AS2) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f4ec3f66a2cdbacf99650620551b7762bcd56df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978365"
---
# <a name="configuring-identifiers-as2"></a>Configuración de identificadores (AS2)
En el acuerdo de socio, debe especificar las entidades de remitente y receptor. Estos valores también se usan para la resolución de acuerdo para los mensajes entrantes o salientes.  
  
> [!IMPORTANT]
>  Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.  
> 
> - **AS2To** en **resoluciones de acuerdos adicionales** sección.  
> 
>   Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-identifier-properties"></a>Procedimiento para configurar las propiedades de identificador  
  
1. Crear un acuerdo AS2 como se describe en [configurar opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2. En una ficha de acuerdo unidireccional, haga clic en **identificadores**.  
  
3. En el **AS2-desde** página, especifique el nombre del socio comercial que envía el mensaje AS2.  
  
4. En el **AS2-para** página, especifique el nombre del socio comercial que recibe el mensaje AS2.  
  
5. En el **resoluciones de acuerdos adicionales** sección, para el **AS2To** propiedad, escriba un alias adicional para el socio que recibe el mensaje.  
  
   > [!NOTE]
   >  Esta propiedad es opcional. Esta propiedad está disponible para la compatibilidad con versiones anteriores. Cuando se migra una definición de la entidad de BizTalk Server 2006 R2 o BizTalk Server 2009 a BizTalk Server, el nombre de la entidad en las versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se incluye como un valor para esta propiedad. Esto garantiza que se produce la resolución del acuerdo y las aplicaciones existentes y definiciones de socio pueden usarse con BizTalk Server.  
  
6. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdo AS2](../core/configuring-as2-agreement-properties.md)
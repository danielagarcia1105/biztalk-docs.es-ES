---
title: "Configuración de la asociación de puerto de envío (EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80d62b919e6d0546f103417af08b52dc3e536ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-send-port-association-edifact"></a>Configuración de la asociación de puerto de envío (EDIFACT)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa la asociación de puertos de envío para resolver un acuerdo para un intercambio EDI saliente. Un intercambio EDI se resuelve para un acuerdo haciendo coincidir el puerto de envío que suscribió el mensaje con el puerto de envío asociado a un acuerdo. Este tema proporciona instrucciones sobre cómo asociar los puertos de envío a un acuerdo.  
  
> [!NOTE]
>  Si el mismo puerto de envío está asociado a varios acuerdos, BizTalk Server generará un error.  
  
> [!IMPORTANT]
>  En [!INCLUDE[prague](../includes/prague-md.md)], la asociación de puertos de envío solo se realiza en el nivel de acuerdo. Sin embargo, en BizTalk Server 2009, los puertos de envío se asociaron en el nivel de entidad. Por compatibilidad con versiones anteriores, un **puertos de envío** página también está disponible como parte de las propiedades de entidad (vea [configurar propiedades de entidad General](../core/configuring-general-party-properties.md)). Siempre que asocie un puerto de envío con un acuerdo, la configuración del puerto de envío se propaga a la configuración de la entidad y también se puede ver la asociación de puerto de envío en esta página. Sin embargo, el proceso inverso no es verdadero. No se puede asociar un puerto de envío con una entidad y, después, hacer que ese puerto de envío esté automáticamente disponible como parte de la configuración del acuerdo.  
  
> [!IMPORTANT]
>  La cuadrícula de asociación de puerto de envío está deshabilitada en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación mientras creaba la entidad para la que va a crear el acuerdo.  
>   
>  La cuadrícula solo se deshabilita en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la cuadrícula está deshabilitada en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-associate-send-ports-with-an-agreement"></a>Para asociar puertos de envío a un acuerdo  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **puertos de envío**.  
  
3.  Haga clic en la celda vacía situada bajo la **nombre** columna y en la lista desplegable, seleccione el puerto de envío para asociar el acuerdo. El **URI** columna muestra la dirección del puerto de envío.  
  
4.  Para quitar una asociación de puerto de envío, seleccione la fila de un puerto de envío y haga clic en **quitar**.  
  
5.  Para ver las propiedades de un puerto de envío, seleccione la fila de un puerto de envío y haga clic en **propiedades**.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (EDIFACT).](../core/configuring-interchange-settings-edifact.md)
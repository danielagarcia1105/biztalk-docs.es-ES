---
title: Cómo configurar el seguimiento de una directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f92e8555c0d644411c165284dd734eb94e6569e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980413"
---
# <a name="how-to-configure-tracking-for-a-policy"></a>Cómo configurar el seguimiento de una directiva
En este tema se describe cómo usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el seguimiento de una directiva. Puede seleccionar diversas opciones para ver datos sobre instancias, resultados de condiciones y actualizaciones de agenda en las vistas de consulta de la página Concentrador de grupo de la consola de administración.  
  
 Para obtener más información sobre la creación y uso de consultas, vea [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md). Para obtener más información acerca de la instancia de mensaje y servicio de seguimiento de las características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [Ver mensaje realiza el seguimiento y datos de instancia](../core/viewing-tracked-message-and-instance-data.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-configure-tracking-for-a-policy"></a>Para configurar el seguimiento de una directiva  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk para los que desea configurar un seguimiento de directiva.  
  
3. Haga clic en **directivas**, haga clic en la directiva, haga clic en **propiedades**y, a continuación, haga clic en **seguimiento**.  
  
4. Seleccione las opciones de seguimiento que desee, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
   |Use|Para|  
   |--------------|----------------|  
   |**Actividad rápida**|Active esta casilla de verificación para realizar un seguimiento de los datos de la instancia en que opera la directiva.|  
   |**Evaluación de condición**|Active esta casilla de verificación para hacer un seguimiento de los resultados true/false de las condiciones de la directiva seleccionada.|  
   |**Activación de reglas**|Active esta casilla de verificación para realizar un seguimiento de las acciones iniciadas como resultado de la directiva.|  
   |**Actualizaciones de agenda**|Active esta casilla de verificación para realizar un seguimiento de las actualizaciones de agenda. La agenda contiene una lista de acciones definidas como “true” que deben activarse.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de directivas](../core/managing-policies.md)
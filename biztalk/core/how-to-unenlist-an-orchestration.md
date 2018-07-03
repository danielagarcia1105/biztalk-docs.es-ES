---
title: Cómo dar de baja una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7504551d6cc97f108d6cdee695f241ee983994a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993517"
---
# <a name="how-to-unenlist-an-orchestration"></a>Cómo dar de baja una orquestación
Este tema explica cómo dar de baja una orquestación mediante la consola de administración de BizTalk Server. Al dar de baja una orquestación, ésta se quita del host. Con ello, se elimina la suscripción, por lo que la orquestación deja de procesar mensajes. Es preciso dar de baja una orquestación antes de poder editar sus enlaces.  
  
 Antes de poder dar de baja una orquestación, es preciso finalizar cualquier instancia en ejecución, como se describe en [cómo suspender, reanudar y finalizar instancias de orquestación](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md).  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede dar de baja una orquestación durante el proceso de desarrollo mediante el procedimiento en este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-unenlist-an-orchestration"></a>Para dar de baja una orquestación  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación que desea dar de baja.  
  
3. Haga clic en **orquestaciones**, haga clic en la orquestación para dar de baja y, a continuación, haga clic en **dar de baja**.  
  
   > [!NOTE]
   >  Para dar de baja varias orquestaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada orquestación para dar de baja, haga clic en una orquestación y, a continuación, haga clic en **dar de baja**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)   
 [Cómo dar de alta una orquestación](../core/how-to-enlist-an-orchestration.md)   
 [Implementación y administración de aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)
---
title: "Cómo dar de alta o baja una entidad para un rol | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [role links], enlisting
- enlisting, role links
- role links, unenlisting
- role links, enlisting
- managing [role links], unenlisting
ms.assetid: 06fc2a64-3add-400c-9f9d-fab22fdf5366
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af988a001e63ba210e5d5c224eeb486800b7286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enlist-or-unenlist-a-party-for-a-role"></a>Cómo dar de alta o de baja una entidad para un rol
En este tema se explica cómo usar la consola de administración de BizTalk Server para dar de alta o de baja una entidad para un rol. Al dar de alta una entidad para un rol, ésta se asigna al rol; por el contrario, al darla de baja, la entidad se quita del rol.  
  
 Al dar de alta o de baja una entidad para un rol, tenga en cuenta los siguientes puntos:  
  
-   Debe crear una entidad antes de darla de alta. Para obtener instrucciones, consulte [cómo crear una entidad](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).  
  
-   Una entidad se puede dar de alta o de baja para un rol sin necesidad de reiniciar la aplicación.  
  
> [!NOTE]
>  El desarrollador de aplicaciones puede dar de alta o baja a una entidad durante el proceso de desarrollo mediante el procedimiento de este tema.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-enlist-or-unenlist-a-party-for-a-role"></a>Para dar de alta o de baja una entidad para un rol  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene el vínculo de función para la que desea dar de alta o dar de baja a una entidad.  
  
3.  Haga clic en **vínculos de función**, haga clic en el vínculo de función para la que desea dar de alta o baja una entidad y, a continuación, haga clic en **propiedades**.  
  
4.  Para dar de alta una entidad, haga lo siguiente:  
  
    -   Haga clic en **dar de alta** y haga clic en la entidad para dar de alta.  
  
    -   Haga clic en **enlazar**, en la **puerto de envío** lista desplegable, haga clic en el envío de puerto para que se utilizará para esta entidad y, a continuación, haga clic en **Aceptar** dos veces.  
  
5.  Para dar de baja una entidad, haga clic en la entidad, haga clic en **dar de baja**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar vínculos de rol](../core/managing-role-links.md)
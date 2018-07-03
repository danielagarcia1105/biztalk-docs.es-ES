---
title: Cómo quitar una referencia a otra aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, references
ms.assetid: cc867706-7c56-4386-b7ec-9fd7cf6c83a4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f995d16d2ef4d45f734058887469863ecabd624
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970611"
---
# <a name="how-to-remove-a-reference-to-another-application"></a>Cómo quitar una referencia a otra aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar una referencia de una aplicación a otra. Las referencias se quitan cuando se deja de utilizar un artefacto en la aplicación actual que existe en otra aplicación del mismo grupo de BizTalk. Para obtener más información sobre cómo agregar referencias, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
 Si los artefactos de la aplicación actual siguen usando artefactos de la otra aplicación, se producirá un error en la operación para quitar la referencia.  
  
> [!CAUTION]
>  Todas las aplicaciones de BizTalk Server contienen automáticamente una referencia a la aplicación BizTalk.System. Ello se debe a que todas las aplicaciones de BizTalk utilizan los artefactos que contiene BizTalk.System. No debe quitar nunca las referencias a la aplicación BizTalk.System. Si lo hace, la aplicación podría no funcionar correctamente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-reference-to-another-application"></a>Para quitar una referencia a otra aplicación  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, haga clic en la aplicación desde el que desea quitar una referencia (la que hace referencia a otra aplicación) y, a continuación, haga clic en **propiedades**.  
  
3. En el panel izquierdo de la página de propiedades, haga clic en **referencias**.  
  
4. En el panel derecho, haga clic en la aplicación que ya no desea hacer referencia desde esta aplicación, haga clic en **quitar**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)
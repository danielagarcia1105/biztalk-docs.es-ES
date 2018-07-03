---
title: Cómo ver las dependencias de un ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b02a773ff51c35de2505336137dfa6c4c11c0825
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001221"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a>Cómo ver las relaciones de dependencia de un ensamblado de BizTalk
En este tema se describe cómo usar la consola de administración de BizTalk Server para ver la lista de artefactos que tienen relaciones de dependencia con un ensamblado de BizTalk. Para obtener información general sobre las dependencias y cómo afectan a la implementación de aplicaciones, consulte [dependencias e implementación de aplicación](../core/dependencies-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento descrito en este tema, debe haber iniciado sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server o del grupo de operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a>Para ver las relaciones de dependencia de un ensamblado de BizTalk  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], el grupo de BizTalk que contiene el ensamblado de BizTalk del que desea ver las relaciones de dependencia y, a continuación, la aplicación que contiene el ensamblado de BizTalk.  
  
3. Haga clic en el **recursos** carpeta, haga clic en el ensamblado de BizTalk y, a continuación, haga clic en **modificar**.  
  
4. Haga clic en el **dependencias** ficha.  
  
    En la lista se muestra el nombre y el estado de los artefactos que tienen relaciones de dependencia con el ensamblado de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Administración de ensamblados de BizTalk](../core/managing-biztalk-assemblies.md)
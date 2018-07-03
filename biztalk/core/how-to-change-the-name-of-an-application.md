---
title: Cómo cambiar el nombre de una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5620bc481f5350e752b71a1706e187016ed25977
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992445"
---
# <a name="how-to-change-the-name-of-an-application"></a>Cómo cambiar el nombre de una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server para cambiar el nombre de una aplicación. Es preciso que el nombre de la aplicación que usa no exista en el grupo.  
  
> [!NOTE]
>  Si ha exportado un archivo MSI de una aplicación que tiene una referencia en la aplicación a la que se ha cambiado el nombre, la referencia ya no funcionará al importar el archivo MSI. Será necesario actualizar la referencia con el nombre nuevo de la aplicación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-change-the-name-of-an-application"></a>Para cambiar el nombre de una aplicación  
  
1. Haga clic en **iniciar**, apunte a **programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**, haga clic en la aplicación cuyo nombre desea cambiar y haga clic en **propiedades**.  
  
3. En el **nombre** , escriba un nombre nuevo para la aplicación y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)
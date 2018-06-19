---
title: Cómo quitar un esquema de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6535764af00156325c006388a88803207329e5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254652"
---
# <a name="how-to-remove-a-schema-from-an-application"></a>Cómo quitar un esquema de una aplicación
En este tema se describe cómo usar la consola de administración de BizTalk Server para quitar un esquema de una aplicación. Este procedimiento quita el esquema de la base de datos de administración de BizTalk y también para el grupo. Puede ser conveniente quitar un esquema después de implementar una versión nueva de él. Para obtener más información y consideraciones importantes para actualizar artefactos de la aplicación, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).  
  
 Cuando se quita un esquema y en la aplicación existe una versión anterior de éste con el mismo espacio de nombres raíz, la versión anterior se convierte en la versión activa.  
  
 Al quitar un esquema, ocurre lo siguiente:  
  
-   El esquema se elimina de la base de datos de administración de BizTalk.  
  
-   El ensamblado de BizTalk que contiene el esquema se elimina de la base de datos de administración de BizTalk, aunque no se quita del sistema de archivos local ni de la caché de ensamblados global (GAC), si existe en estas ubicaciones.  
  
-   Como consecuencia de la eliminación del ensamblado de BizTalk, también se quitan de la base de datos de administración de BizTalk todos los artefactos que contiene el ensamblado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-remove-a-schema"></a>Para quitar un esquema  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el esquema para quitar y la aplicación que contiene el esquema.  
  
3.  Haga clic en **esquemas**, haga clic en el esquema y, a continuación, haga clic en **quitar**.  
  
## <a name="see-also"></a>Vea también  
 [Administrar esquemas](../core/managing-schemas.md)
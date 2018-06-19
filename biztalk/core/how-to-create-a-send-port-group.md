---
title: Cómo crear un grupo de puertos de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33d27914dd5d7ae59b0823c2e6009ab307c41b9b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970370"
---
# <a name="how-to-create-a-send-port-group"></a>Cómo crear un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para crear un grupo de puertos de envío en una aplicación de BizTalk para, a continuación, agregarle puertos de envío. Puede agregar puertos de envío unidireccional estático únicamente a un grupo de puertos de envío. Para enrutar mensajes, un grupo de puertos de envío debe contener, como mínimo, un puerto de envío.  
  
 Es posible agregar un puerto de envío existente en una aplicación diferente. Si lo hace, tendrá que agregar una referencia de la aplicación que contenga el grupo de puertos de envío a la que contenga el puerto de envío. Para obtener instrucciones, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-create-a-send-port-group"></a>Para crear un grupo de puertos de envío  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk en los que desee crear un grupo de puertos de envío.  
  
3.  Haga clic en **grupos de puertos de envío**, seleccione **New**y, a continuación, haga clic en **grupo de puertos de envío**.  
  
4.  En el **nombre** , escriba un nombre para el grupo de puertos de envío.  
  
5.  En **puertos de envío**, haga clic en la lista desplegable bajo **nombre**y haga clic en el puerto de envío para agregar al grupo de puertos de envío. Repita esta acción con cada uno de los puertos de envío que desee agregar al grupo. Para crear un nuevo puerto de envío y agregarlo, haga clic en  **\<nuevo puerto de envío... \>**  y, a continuación, siga las instrucciones que aparecen en [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
6.  Cuando termine de agregar puertos de envío para el grupo de puertos de envío, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)
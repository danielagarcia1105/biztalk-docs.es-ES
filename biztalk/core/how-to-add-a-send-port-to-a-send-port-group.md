---
title: Cómo agregar un puerto de envío a un grupo de puertos de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6c2b616952aa4f24e40ddd56e035a6de4a77c58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007181"
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a>Cómo agregar un puerto de envío a un grupo de puertos de envío
En este tema se describe cómo utilizar la consola de administración de BizTalk Server para agregar uno o varios puertos de envío a un grupo de puertos de envío. Solo se pueden agregar puertos de envío estáticos unidireccionales a un grupo de puertos de envío.  
  
 Es posible agregar un puerto de envío existente en una aplicación diferente. Si lo hace, tendrá que agregar una referencia de la aplicación que contenga el grupo de puertos de envío a la que contenga el puerto de envío. Para obtener instrucciones, consulte [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a>Para agregar un puerto de envío a un grupo de puertos de envío  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda el grupo de BizTalk y la aplicación de BizTalk a cuyos grupos de puertos de envío desee agregar un puerto de envío.  
  
3. Haga clic en **grupos de puertos de envío**, haga clic en el grupo de puertos de envío y, a continuación, haga clic en **propiedades**.  
  
4. En **puertos de envío**, haga clic en la lista desplegable bajo **nombre**y haga clic en el puerto de envío para agregar al grupo de puertos de envío. Repita esta acción con cada uno de los puertos de envío que desee agregar al grupo. Para crear un nuevo puerto de envío y agregarlo, haga clic en **\<nuevo puerto de envío... \>** y, a continuación, siga las instrucciones de [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
5. Cuando termine de agregar puertos de envío para el grupo de puertos de envío, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Crear y configurar grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)   
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)
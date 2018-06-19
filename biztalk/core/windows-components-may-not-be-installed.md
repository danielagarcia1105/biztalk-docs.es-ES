---
title: Pueden que no estén instalados los componentes de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506f9c310a75c9f65564e4feb047157731bafa66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289860"
---
# <a name="windows-components-may-not-be-installed"></a>Quizá no se instalen los componente de Windows
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Pueden que no estén instalados los siguientes componentes de Windows: servidor de aplicaciones -&gt; Internet Information Services (IIS) -&gt; archivos comunes.|  
  
## <a name="explanation"></a>Explicación  
 Este error se producirá cuando se intente la publicación sin tener instalado Internet Information Services (IIS) en el equipo local.  
  
## <a name="user-action"></a>Acción del usuario  
 En Windows 7 y Windows Vista SP2, instale IIS en el equipo local y configure IIS de la siguiente forma:  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**y haga clic en **programas**.  
  
2.  Haga clic en **o desactivar las características de Windows Active**. Aparece el Asistente para Características de Windows.  
  
3.  Para agregar, compruebe el componente IIS.  
  
 En [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale IIS en la máquina local y configure IIS de la siguiente forma:  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**y haga clic en **herramientas administrativas**.  
  
2.  Haga clic en **el administrador del servidor**. Aparece la ventana del administrador de servidores.  
  
3.  Haga clic en **agregar Roles**, aparece el Asistente para agregar Roles.  
  
4.  Para agregar, seleccione componente de IIS.
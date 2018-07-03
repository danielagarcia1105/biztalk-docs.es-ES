---
title: No se pueden instalar componentes de Windows | Microsoft Docs
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
ms.openlocfilehash: d61ded5b2ddb077ff0851c20d673fad4f9de9d26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975509"
---
# <a name="windows-components-may-not-be-installed"></a>Quizá no se instalen los componente de Windows
## <a name="details"></a>Detalles  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| Versión del producto |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    Identificador del evento     |                                                                   0                                                                    |
|  Origen del evento   |                                                                   0                                                                    |
|    Componente    |                                                                   0                                                                    |
|  Nombre simbólico  |                                                                   0                                                                    |
|  Texto del mensaje   | No se puede instalar el siguiente componente de Windows: servidor de aplicaciones -&gt; Internet Information Services (IIS) -&gt; archivos comunes. |

## <a name="explanation"></a>Explicación  
 Este error se producirá cuando se intente la publicación sin tener instalado Internet Information Services (IIS) en el equipo local.  

## <a name="user-action"></a>Acción del usuario  
 En Windows 7 y Windows Vista SP2, instale IIS en el equipo local y configure IIS de la siguiente forma:  

1. Haga clic en **iniciar**, haga clic en **Panel de Control**y haga clic en **programas**.  

2. Haga clic en **y desactivar las características de Windows Active**. Aparece el Asistente para Características de Windows.  

3. Para agregar, compruebe el componente IIS.  

   En [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], instale IIS en la máquina local y configure IIS de la siguiente forma:  

4. Haga clic en **iniciar**, haga clic en **Panel de Control**y haga clic en **herramientas administrativas**.  

5. Haga clic en **administrador del servidor**. Aparece la ventana del administrador de servidores.  

6. Haga clic en **agregar Roles**, aparece el Asistente para agregar Roles.  

7. Para agregar, seleccione componente de IIS.

---
title: Anular la implementación de otros proyectos del Tutorial | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e5c4d7e20fc4d8e7c8bea724625dde770b4aca2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006421"
---
# <a name="undeploy-other-tutorial-projects"></a>Anular la implementación de otros proyectos del Tutorial
Cuando se implementa un acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutoriales, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] almacena los archivos de ensamblado del tutorial en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché global de ensamblados. Si ha ejecutado otro [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial e implementado los ensamblados que creó en este tutorial, podría experimentar errores al probar los ensamblados en las tres partes del tutorial de procesamiento por lotes. Esto puede ocurrir porque solo se puede implementar un esquema de mensaje al mismo tiempo.  
  
 Puede evitar estos errores al anular la implementación de los ensamblados que haya implementado en los tutoriales anteriores. Puede volver a desplegar el ensamblado más adelante si es necesario.  
  
 Antes de anular la implementación de un ensamblado, debe dar de baja orquestaciones del ensamblado. También debe quitar cualquier referencia al ensamblado que desea anular la implementación, desde cualquier otro ensamblado que desea mantener implementado. Una alternativa consiste en eliminar todos los archivos DLL asociado con un tutorial, antes de iniciar otro tutorial.  
  
### <a name="to-undeploy-an-assembly"></a>Para anular la implementación de un ensamblado  
  
1.  Dar de baja orquestaciones usadas en el ensamblado que desea anular la implementación haciendo clic en la orquestación en el Explorador de BizTalk de Visual Studio y, a continuación, haga clic en **dar de baja**.  
  
2.  En cualquier ensamblado que se desea mantener implementado, quite las referencias a los ensamblados que desea anular la implementación. Haga clic en la referencia en el Explorador de soluciones y, a continuación, haga clic en **quitar**.  
  
3.  Abra el Explorador de BizTalk, haga clic en el ensamblado que desea anular la implementación y, a continuación, haga clic en **anular la implementación**.  
  
 Para obtener más información acerca de cómo anular la implementación de un ensamblado, vea "Anular la implementación un ensamblado utilizando el Explorador de BizTalk" en la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Preparación para usar el tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)
---
title: Anular la implementación de otros proyectos del Tutorial | Microsoft Docs
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
ms.openlocfilehash: e2c014a094acac4e374605cd0ebd9b9c50c9d733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976285"
---
# <a name="undeploy-other-tutorial-projects"></a>Anular la implementación de otros proyectos del Tutorial
Al implementar un acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutoriales, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] almacena los archivos de ensamblado del tutorial en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché global de ensamblados. Si ha ejecutado otra [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial e implementar los ensamblados creados en ese tutorial, que pueden producirse errores al probar los ensamblados en las tres partes del tutorial de procesamiento por lotes. Esto puede ocurrir porque solo se puede implementar un esquema de mensaje al mismo tiempo.  
  
 Puede evitar estos errores al anular la implementación de los ensamblados que haya implementado en los tutoriales anteriores. Puede volver a desplegar el ensamblado más adelante si es necesario.  
  
 Antes de anular la implementación de un ensamblado, debe dar de baja las orquestaciones del ensamblado. También debe quitar cualquier referencia al ensamblado que desea anular la implementación de cualquier otro ensamblado que desea que tenga implementado. Una alternativa consiste en eliminar todos los archivos DLL asociados con un tutorial, antes de iniciar otro tutorial.  
  
### <a name="to-undeploy-an-assembly"></a>Para anular la implementación de un ensamblado  
  
1. Dar de baja las orquestaciones utilizadas en el ensamblado que desea anular la implementación haciendo clic en la orquestación en el Explorador de BizTalk de Visual Studio y, a continuación, haga clic en **dar de baja**.  
  
2. En cualquier ensamblado que desea que tenga implementada, quitar las referencias a ensamblados que desea anular la implementación. A la derecha, haga clic en la referencia en el Explorador de soluciones y, a continuación, haga clic en **quitar**.  
  
3. Abra el Explorador de BizTalk, haga clic en el ensamblado que desea anular la implementación y, a continuación, haga clic en **Undeploy**.  
  
   Para obtener más información sobre cómo anular la implementación de un ensamblado, vea "Anular la implementación un ensamblado utilizando el Explorador de BizTalk" en la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Preparación para usar el tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)
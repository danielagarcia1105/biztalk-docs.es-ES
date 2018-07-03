---
title: 'Lección 4: Crear e implementar el ensamblado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 867fe91ad0dd8dcb00c0293da08753f38e5005d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988277"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a>Lección 4: Crear e implementar el ensamblado
En esta lección, compilar e implementar el proyecto para generar un ensamblado que contiene los esquemas creados en las lecciones anteriores. Esta tarea garantiza que no hay ningún error de compilación en el trabajo que ha creado hasta ahora.  
  
 Implementar un ensamblado coloca una copia del ensamblado en la base de datos de configuración y lo instala en la caché global de ensamblados (GAC). En el siguiente procedimiento, se implementa directamente desde el Explorador de soluciones.  
  
 Cuando el proyecto se compila en un ensamblado (archivo DLL), Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] guarda el archivo DLL en el \< *unidad*\>: \Program archivos\\Acelerador de Microsoft BizTalk para SWIFT\bin\ Carpeta de desarrollo dentro de la carpeta del proyecto.  
  
### <a name="to-build-and-deploy-the-project"></a>Procedimiento para generar e implementar el proyecto  
  
1. En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **compilar**.  
  
   > [!NOTE]
   >  Compruebe que **compilación correcta** aparece en la esquina inferior izquierda de la pantalla. Durante el proceso de compilación, puede ver algunos mensajes de estado. Estos mensajes son normales cuando se trabaja con los esquemas SWIFT. Si aparece algún error, haga clic en herramientas y, a continuación, haga clic en administración de BizTalk Server para abrir la consola de administración de BizTalk Server. Usar la característica Visor de eventos y el mantenimiento y seguimiento de actividad (HAT) en la consola de administración de BizTalk para corregir los errores y vuelva a generar.  
  
2. Uso de [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] explorador, vaya a la  **\< *unidad*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development** carpeta y compruebe que el  **SWIFTSchemas.dll** archivo existe en esta carpeta.  
  
3. En el Explorador de soluciones, haga clic en **SWIFTSchemas**y, a continuación, haga clic en **implementar**.  
  
   > [!NOTE]
   >  Compruebe que **operación implementar finalizada correctamente** aparece en la esquina inferior izquierda de la pantalla.  
  
### <a name="to-confirm-deployment-success"></a>Para confirmar el éxito de la implementación  
  
1. Haga clic en **vista** y, a continuación, haga clic en **el Explorador de BizTalk**.  
  
2. Expanda el **ensamblados** nodo y confirme que **SWIFTSchemas (1.0.0.0)** aparece en la lista.  
  
    Si SWIFTSchemas aparece en la lista, el ensamblado implementado correctamente y se puede hacer referencia a y usar de otros [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proyectos.  
  
   Continúe con [módulo 3: agregar un proyecto de canalización](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md).
---
title: 'Paso 7: Firmar y compilar los proyectos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, projects
- projects, building
- projects, signing
ms.assetid: b66e4dc1-4ec6-4ec0-a69a-419b116b19c1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f62a37da291bdc148369a28149cdfe29ed7fe446
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-7-sign-and-build-the-projects"></a>Paso 7: Firmar y compilar los proyectos
En este paso, se asigna un nombre seguro y generar el proyecto para generar un ensamblado que contiene los recursos (el esquema) que creó en [paso 6: validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md). Esto también garantiza que no hay ningún error de compilación en el trabajo que ha completado hasta ahora.  
  
### <a name="to-sign-the-btahl7-project"></a>Para firmar el proyecto de BTAHL7  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades del proyecto de BTAHL7, haga clic en **ensamblado**.  
  
3.  En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
4.  En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*\>: \Tutorial\BTAHL7V22Common\key.snk** (como se crearon en [paso 3: asignar un nombre seguro para el Ensamblado](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)) y, a continuación, haga clic en **abiertos**.  
  
5.  Haga clic en **Aceptar** para guardar los cambios.  
  
### <a name="to-build-the-btahl7-project"></a>Para compilar el proyecto de BTAHL7  
  
-   En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**y, a continuación, haga clic en **implementar**. [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]compila el ensamblado en un archivo DLL y lo guarda en la \< *unidad*\>: \Tutorial\BTAHL7V22Common\Bin\Development carpeta.  
  
 Continúe con [paso 8: crear un mapa con el asignador de BizTalk](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)
---
title: Herramientas de tiempo de diseño | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- BTAHL7, tools
- Starter Project
- Pipeline Designer
- BizTalk Editor
- Visual Studio Starter Project
- BizTalk Mapper
- design-time tools
- Orchestration Designer
ms.assetid: 709bd782-d2ad-49be-ba33-e957eba2a0cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1253de9aa3bc7e45324402d5de6d4705ecf8f92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005053"
---
# <a name="design-time-tools"></a>Herramientas de tiempo de diseño
Los desarrolladores que trabajan en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tiene el uso de un conjunto de herramientas en tiempo de diseño integrada en BizTalk Server. Estas herramientas están integradas en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools, vea [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ayuda de BizTalk Server.  
  
## <a name="biztalk-editor"></a>Editor de BizTalk  
 Utilice el Editor de BizTalk para administrar esquemas XSD HL7. Puede usar las siguientes plantillas de esquemas admitidas (como archivos XSD) para el desarrollo de soluciones:  
  
-   HL7: 2.1 (incluye 37 eventos)  
  
-   HL7: 2.2 (incluye 56 eventos)  
  
-   HL7: 2.3 (incluye 182 eventos)  
  
-   HL7: 2.3.1 (incluye 189 eventos)  
  
-   HL7: 2.4 (incluye eventos de 288)  
  
-   HL7: 2.5 (incluye aproximadamente 390 esquemas)  
  
-   HL7: 2. XML (incluye aproximadamente 450 esquemas para V2.3.1 y 2.4)  
  
## <a name="biztalk-mapper"></a>Asignador de BizTalk  
 Utilice al asignador de BizTalk para crear y personalizar las asignaciones que definen transformaciones de datos. Utilice el asignador de BizTalk para asignar las transformaciones de entrada y salida [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tipos de mensaje.  
  
## <a name="biztalk-orchestration-designer"></a>Diseñador de orquestaciones de BizTalk  
 Utilice el Diseñador de orquestaciones de BizTalk para diseñar e implementar procesos empresariales.  
  
## <a name="biztalk-pipeline-designer"></a>Diseñador de canalizaciones de BizTalk  
 Utilice el Diseñador de canalizaciones de BizTalk para crear y configurar las canalizaciones que definen y pasos de procesamiento de vínculo. Las canalizaciones dividen el procesamiento en fases y determinan la secuencia en que se realiza cada categoría de trabajo.  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]proporciona tanto de recepción y transmisión de canalizaciones para todas las versiones compatibles de HL7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Proporciona una plantilla de canalización que tenga un analizador de HL7 personalizado y un componente de desensamblador/ensamblador.  
  
## <a name="biztalk-adapter-framework"></a>Adaptador de BizTalk Framework  
 Utilice el adaptador de BizTalk Framework con adaptadores de extremo para la integración con socios y aplicaciones.  
  
## <a name="visual-studio-starter-project"></a>Proyecto de inicio de Visual Studio  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]incluye el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] proyecto de inicio, que puede usar para la implementación de soluciones de HL7 de inicio rápido. El proyecto de inicio incluye los siguientes proyectos:  
  
-   **Vacía**[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**proyecto**. No incluye todos los esquemas.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V2XCommon proyecto**. Incluye los esquemas de encabezado y confirmación.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V21Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.1.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V22Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.2.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V23Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.3.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V231Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.3.1.  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**V24Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.4.  
  
-   BTAHL7**V25Common proyecto**. Incluye los esquemas comunes para HL7 versión 2.5.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y características](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md)   
 [Herramientas de análisis](../../adapters-and-accelerators/accelerator-hl7/analysis-tools2.md)
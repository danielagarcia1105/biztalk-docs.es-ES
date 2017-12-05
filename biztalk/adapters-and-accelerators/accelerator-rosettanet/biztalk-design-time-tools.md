---
title: "Herramientas de tiempo de diseño de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- schemas, tools
- BizTalk Orchestration Designer
- schemas, BTARN schemas
- BizTalk Editor
- BizTalk Mapper
- tools, schemas
- BTARN, schemas
- BizTalk Pipeline Designer
ms.assetid: a981e167-f178-4fef-be0e-02fa15feffc2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f259167112ab87da5af14ca73f735ae38d8789e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="biztalk-design-time-tools"></a>Herramientas de tiempo de diseño de BizTalk
Los desarrolladores que trabajan en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] puede usar el conjunto de herramientas en tiempo de diseño integrada en BizTalk Server. Estas herramientas están integradas en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]. Para obtener más información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools, vea [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ayuda de BizTalk Server.  
  
## <a name="biztalk-editor"></a>Editor de BizTalk  
 Usar el Editor de BizTalk para administrar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] esquemas XSD que se basan en procesos de interfaz de socio (PIP) RosettaNet. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]instala los siguientes esquemas para el desarrollo de soluciones:  
  
-   0A1_FailureNotificationPropertySchema.xsd  
  
-   0A1_MS_V02_00_FailureNotification.xsd  
  
-   0A1_V1_FailureNotificationMessageGuideline.xsd  
  
-   0C1_MS_R01_02_AsynchronousTestNotification.xsd  
  
-   0C2_MS_R01_02_AsynchronousTestConfirmation.xsd  
  
-   0C2_MS_R01_02_AsynchronousTestRequest.xsd  
  
-   0C3_MS_R01_02_SynchronousTestNotification.xsd  
  
-   0C4_MS_R01_02_SynchronousTestQuery.xsd  
  
-   0C4_MS_R01_02_SynchronousTestResponse.xsd  
  
-   2A12_MS_V01_03_ProductMasterNotification.xsd  
  
-   3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.xsd  
  
-   3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.xsd  
  
-   3A4_MS_V02_02_PurchaseOrderConfirmation.xsd  
  
-   3A4_MS_V02_02_PurchaseOrderRequest.xsd  
  
 Estos esquemas están disponibles en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas.  
  
 Puede agregar varios esquemas mediante la descarga PIP desde el sitio RosettaNet Web en [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859). Para obtener más información, consulte [incorpora un nuevo proceso de interfaz de socio comercial](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).  
  
## <a name="biztalk-mapper"></a>Asignador de BizTalk  
 Utilice al asignador de BizTalk para crear y personalizar las asignaciones que definen transformaciones de datos. Utilice al asignador de BizTalk para asignar las transformaciones de tipos de mensajes entrantes y salientes de RosettaNet.  
  
## <a name="biztalk-orchestration-designer"></a>Diseñador de orquestaciones de BizTalk  
 Utilice el Diseñador de orquestaciones de BizTalk para diseñar e implementar procesos empresariales. Puede personalizar los procesos privados proporcionados en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK. Para obtener más información, vea [procesos privados &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) y [personalizar procesos privados &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/customizing-private-processes.md). No se pueden personalizar procesos públicos; hacerlo podría invalidar su cumplimiento de RosettaNet.  
  
## <a name="biztalk-pipeline-designer"></a>Diseñador de canalizaciones de BizTalk  
 Utilice el Diseñador de canalizaciones de BizTalk para crear y configurar las canalizaciones que definen y vinculan los pasos de procesamiento de mensajes. Canalizaciones dividen en fases de procesamiento de mensajes y determinan la secuencia en que se realiza cada categoría de trabajo.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye tanto de recepción y transmisión de canalizaciones de RosettaNet Implementation Framework (RNIF). Para obtener más información, consulte [RNIF canalizaciones](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md).  
  
## <a name="biztalk-adapter-framework"></a>Adaptador de BizTalk Framework  
 Utilice el adaptador de BizTalk Framework con adaptadores de extremo para la integración con socios y aplicaciones.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y características de BizTalk Server y BTARN](../../adapters-and-accelerators/accelerator-rosettanet/tools-and-features-of-biztalk-server-and-btarn.md)   
 [Herramientas de administración y tiempo de ejecución](../../adapters-and-accelerators/accelerator-rosettanet/administration-and-run-time-tools.md)   
 [Herramientas de análisis](../../adapters-and-accelerators/accelerator-rosettanet/analysis-tools1.md)   
 [Incorporación de un nuevo proceso de interfaz de socio comercial](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)
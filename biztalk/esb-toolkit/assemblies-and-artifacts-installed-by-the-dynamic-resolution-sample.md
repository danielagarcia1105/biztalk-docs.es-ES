---
title: "Ensamblados y artefactos instalados en el ejemplo de resolución dinámica | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d9ffdc4-1721-4202-839c-04e5bffe8668
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f564d2faceca0753d37bd9c045e403f5f016734
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-dynamic-resolution-sample"></a>Ensamblados y artefactos instalados en el ejemplo de resolución dinámica
En la tabla siguiente se enumera los ensamblados y artefactos instalados por la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplo de resolución dinámica.  
  
|Ubicación|Categoría|Nombre y versión del componente|  
|--------------|--------------|---------------------------------------|  
|Aplicación de BizTalk GlobalBank.ESB|Orquestaciones|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de envío|DynamicResolutionSolicitResp|  
|||DynamicResolutionOneWay|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de recepción|DynamicResolutionReqResp|  
|||DynamicResolution|  
|Aplicación de BizTalk GlobalBank.ESB|Ubicaciones de recepción|DynamicResolutionReqResp_SOAP<br /><br /> DynamicResolution_FILE|  
|Aplicación de BizTalk GlobalBank.ESB|Esquemas|GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderResponse versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderResponse versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderDoc versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderResponse versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderDoc versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Canalizaciones|GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveSendXMLXML versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveXML versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBPassThrough versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Recursos|GlobalBank.ESB.DynamicResolution.Pipelines versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms versión 2.0.0.0|  
|Aplicación de BizTalk GlobalBank.ESB|Directivas|CanadaSubmitOrderMaps.xml|  
|||GetCanadaEndPoint.xml|  
|||GetCanadaPurchaseEndPoint.xml|  
|||ResolveMap.xml|  
|||ResolveEndPoint.xml|  
|Aplicación de BizTalk GlobalBank.ESB|Vocabularios|DynamicRunTimeDocSpecs.xml<br /><br /> DynamicRunTimeEndPoints.xml<br /><br /> DynamicRunTimeMapTypes.xml<br /><br /> DynamicRunTimeServiceActions.xml|  
|Aplicación de BizTalk GlobalBank.ESB|Mapas|Versión de GlobalBank.ESB.DynamicResolution.Transforms.SubmitPurchaseOrderResponseCN_To_SubmitOrderResponseNA = 2.0.0.0|  
|||Versión de GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN = 2.0.0.0|  
|||Versión de GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitPurchaseOrderRequestCN = 2.0.0.0|  
|||Versión de GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderResponseCN_To_SubmitOrderResponseNA = 2.0.0.0|  
|Caché global de ensamblados|Ensamblados|GlobalBank.ESB.DynamicResolution.Pipelines versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas versión 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms versión 2.0.0.0|  
|% Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline componentes|Componentes de canalización|(ninguno)|
---
title: Las operaciones que son compatibles con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing by using the adapter
ms.assetid: 800cf44b-357f-4850-8878-f49ceb549adf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3f080cedb74210d02806681b6c9e20656d3d09e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004781"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a>Las operaciones que son compatibles con el adaptador de Siebel
Los clientes del adaptador pueden realizar operaciones en el sistema de Siebel, ya sea por:  
  
- Crear proyectos de BizTalk.  
  
- Mediante el modelo de canal WCF.  
  
- Mediante el modelo de servicio WCF.  
  
  La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone las operaciones que las aplicaciones pueden invocar en él y que a su vez, puede invocar en las aplicaciones. Estas operaciones se invocan mediante el envío de mensajes SOAP a través de un canal. Si se requiere una respuesta, se devuelve en un mensaje SOAP a través del canal mismo. Para obtener información acerca de la estructura del mensaje y la acción de SOAP asociada con cada operación, vea [mensajes y esquemas de mensaje para el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
  
  Esta sección proporciona información acerca de las operaciones admitidas en el sistema de Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
> [!NOTE]
>  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite la recepción de las llamadas entrantes de un sistema Siebel.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Operaciones en componentes empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [Operaciones en servicios empresariales de Siebel](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)
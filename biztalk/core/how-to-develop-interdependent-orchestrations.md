---
title: Cómo desarrollar orquestaciones interdependientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6375add6d27e6ce0d3dff89bd2b172a2b693356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992405"
---
# <a name="how-to-develop-interdependent-orchestrations"></a>Cómo desarrollar orquestaciones interdependientes
Puede usar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para desarrollar un conjunto de orquestaciones que tienen servicios Web interdependientes. Esta situación se produce al tener orquestaciones que hacen referencia a tipos de datos o puertos en la orquestación desde las que se les llama. Un ejemplo de este tipo de escenario se caracteriza por lo siguiente:  
  
- Tiene dos o más orquestaciones.  
  
- La primera orquestación (Orq1) llama a la segunda orquestación (Orq2) con una llamada de servicio Web unidireccional.  
  
- Orq2 responde a Orq1 con una llamada de servicio Web.  
  
  Para obtener un ejemplo de este tipo de proyecto, vea [Tutorial 2: proceso de pedido de compra](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467).  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a>Para desarrollar dos orquestaciones interdependientes (Orq1 y Orq2)  
  
1. Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree una versión parcial de la orq1 que tiene un puerto de recepción que se expondrá como un servicio Web.  
  
2. Compile Orq1.  
  
3. Ejecute el Asistente para publicar servicios Web y publique el puerto.  
  
4. Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree y complete toda la orq2, consumir servicio web de orq1.  
  
5. Compile Orq2.  
  
6. Ejecute el Asistente para publicar servicios Web y publique los puertos.  
  
7. Complete Orq1, que utiliza el servicio Web de Orq2, según sea necesario.  
  
8. Vuelva a compilar Orq1.  
  
9. Implemente Orq1 y Orq2.  
  
## <a name="see-also"></a>Vea también  
 [Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como un servicio Web](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)
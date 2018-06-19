---
title: Operaciones de Windows Communication Foundation | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263772"
---
# <a name="operations-in-windows-communication-foundation"></a>Operaciones en Windows Communication Foundation
Esta sección contiene las operaciones personalizadas que admite el interceptor de WCF de BAM.  
  
 Si un elemento de nombre de operación contiene un atributo Acción, tenga en cuenta que:  
  
1.  El nombre de la operación es el identificado mediante el atributo de nombre para el cliente y el servidor.  
  
2.  En el caso de rutas de respuesta (respuesta de devolución), respuesta del cliente y del servicio, el nombre de la operación se identifica mediante el atributo del nombre.  
  
> [!NOTE]
>  El nombre del nodo de los mensajes de respuesta se asignará anexando la palabra "Resultado" al nombre especificado por el atributo de nombre. Debe asegurarse de que los XPaths reflejen esta convención de nomenclatura.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Autogeneratecorrelationtoken (operación)](../core/autogeneratecorrelationtoken.md)  
  
-   [Getcontextproperty (operación)](../core/getcontextproperty1.md)  
  
-   [GetEndpointName](../core/getendpointname.md)  
  
-   [Getoperationname (operación)](../core/getoperationname.md)  
  
-   [Getservicecontractcallpoint (operación)](../core/getservicecontractcallpoint.md)  
  
-   [XPath](../core/xpath.md)
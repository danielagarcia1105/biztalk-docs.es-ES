---
title: El componente de distribuidor ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294908"
---
# <a name="the-esb-dispatcher-component"></a>El componente de distribuidor ESB
Basado en mensajería itinerarios servicios se ejecutan en el componente de distribuidor de ESB. El componente de distribuidor puede establecer propiedades de ubicación de punto de conexión para los mensajes salientes también dinámicamente y transformar mensajes de forma dinámica.  
  
## <a name="component-properties"></a>Propiedades de componente  
 El componente de distribuidor tiene seis propiedades:  
  
-   **RoutingServiceName**. Esta propiedad especifica el nombre registrado para el servicio de enrutamiento basado en mensajería. El valor predeterminado es **Microsoft.Practices.ESB.Services.Routing**.  
  
-   **TransformServiceName**. Esta propiedad especifica el nombre registrado para el servicio de transformación basado en mensajería. El valor predeterminado es **Microsoft.Practices.ESB.Services.Transform**.  
  
-   **Validar**. Esta propiedad especifica si es necesario validar un mensaje.  
  
-   **Habilitado**. Esta propiedad habilita o deshabilita el componente.  
  
-   **Punto de conexión**. Esta propiedad es una cadena de conexión de resolución en un formato registrado con el Kit de herramientas de BizTalk ESB.  
  
-   **Asignar nombre**. Esta propiedad es el nombre completo de un mapa o un formato de cadena de conexión registrado en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
    -   El siguiente es un ejemplo de un nombre de mapa:  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```
---
title: El componente de distribuidor ESB | Microsoft Docs
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
ms.openlocfilehash: 16281ff49da6470212e9e8396a051270adf1eef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982133"
---
# <a name="the-esb-dispatcher-component"></a>El componente de distribuidor ESB
Servicios de itinerario basada en mensajería se ejecutan dentro del componente de distribuidor de ESB. El componente de distribuidor puede establecer propiedades de ubicación de punto de conexión para los mensajes salientes también dinámicamente y transformar mensajes de forma dinámica.  
  
## <a name="component-properties"></a>Propiedades de componente  
 El componente de distribuidor tiene seis propiedades:  
  
- **RoutingServiceName**. Esta propiedad especifica el nombre registrado para el servicio de enrutamiento basado en mensajería. El valor predeterminado es **Microsoft.Practices.ESB.Services.Routing**.  
  
- **TransformServiceName**. Esta propiedad especifica el nombre registrado para el servicio de transformación basado en mensajería. El valor predeterminado es **Microsoft.Practices.ESB.Services.Transform**.  
  
- **Validar**. Esta propiedad especifica si un mensaje necesita ser validada.  
  
- **Habilitado**. Esta propiedad habilita o deshabilita el componente.  
  
- **Punto de conexión**. Esta propiedad es una cadena de conexión de la resolución en un formato registrado con el Kit de herramientas de BizTalk ESB.  
  
- **Asignar nombre**. Esta propiedad es el nombre completo de un mapa o registrarse en un formato de cadena de conexión [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:  
  
  -   Este es un ejemplo de un nombre de mapa:  
  
      ```  
      GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
      ```
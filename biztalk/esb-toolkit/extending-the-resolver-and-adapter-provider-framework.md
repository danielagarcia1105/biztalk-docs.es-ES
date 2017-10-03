---
title: "Extender la resolución y el marco de proveedores de adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ab5caf03d113e313e00a74c11641058e86b886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a>Extender la resolución y el marco de proveedores de adaptador
La resolución y el marco de proveedores de adaptador proporciona compatibilidad para el punto de conexión y la resolución de transformación y del enrutamiento, y también puede proporcionar metadatos personalizados para los servicios. El marco de trabajo puede resolver los puntos de conexión y establecer las propiedades de salida del adaptador dinámicamente. Después de la resolución de una componente resuelve un punto de conexión (por ejemplo, con Universal Description, Discovery e integración [UDDI] para buscar una dirección URL saliente), un componente de proveedor de adaptador establece propiedades específicas de los adaptadores de Microsoft BizTalk Server registrados.  
  
 Hay tres áreas principales donde puede ampliar la resolución y el marco de proveedores de adaptador:  
  
-   [Crear a una resolución personalizada](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [Crear a una resolución personalizada con un contenedor de Unity](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [Crear un proveedor de adaptador personalizado](../esb-toolkit/creating-a-custom-adapter-provider.md)
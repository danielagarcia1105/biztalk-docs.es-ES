---
title: "Nueva página de entrada de registro | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 204c547c-ed0e-4a1f-a0b2-ce5da00d9c42
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56fa56bff9d1418cc54430a6ab61140821a4ccc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="new-registry-entry-page"></a>Página de entrada de nuevo registro
Figura 1 muestra la página de Portal de administración de ESB de nueva entrada de registro donde puede ver una lista de los puntos de conexión existentes en una aplicación de Microsoft BizTalk Server ESB especificada.  
  
 ![Nueva página de entrada de registro](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8-NewRegistryEntryPage")  
  
 **Figura 1**  
  
 **La página de Portal de administración de ESB de nueva entrada de registro**  
  
 En la lista siguiente se explica cómo puede usar las características de la página de Portal de administración de ESB de nueva entrada de registro:  
  
-   Utilice las tres listas de lista desplegable en la parte superior de la página para especificar el tipo, el estado y la aplicación de BizTalk que contiene los extremos que desea ver:  
  
    -   En la primera lista de la lista desplegable (tipo de extremo), puede seleccionar **ubicaciones de recepción, puertos de envío,** o **todos los extremos**.  
  
    -   En la segunda lista de desplegable (estado), puede seleccionar **registrado, no registrado, pendiente,** o **todos los**.  
  
    -   En la tercera lista de desplegable (aplicación de BizTalk), puede seleccionar una de las aplicaciones de BizTalk instaladas actualmente.  
  
-   Después de especificar los criterios de aplicación y el punto de conexión, haga clic en el icono de flecha junto a la lista de desplegable de aplicación de BizTalk para mostrar una lista de puntos de conexión coincidentes.  
  
-   La lista de puntos de conexión contiene detalles de coincidencia de los puntos de conexión. En cada caso que no es un punto de conexión dinámica, la lista contiene un vínculo que permite ver y editar los detalles de una solicitud pendiente para publicar este punto de conexión.  
  
-   Haga clic en el **Ver detalle** vínculo en cualquier fila de la lista para abrir el [página de detalles de registro](../esb-toolkit/registry-details-page.md) donde puede modificar la solicitud y publicar el punto de conexión.
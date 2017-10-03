---
title: Optimizar el rendimiento de red | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6c3985a-48b3-489b-8fe3-3b7bfd0515f9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8225bd082140ac1347bc99a91ea209f9d79a8bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-network-performance"></a>Optimizar el rendimiento de red
En un entorno de BizTalk Server donde el equipo de BizTalk Server es independiente del equipo de SQL Server, cada mensaje procesado por el servidor BizTalk Server requiere comunicación a través de la red. Esta comunicación incluye el tráfico considerable entre el equipo de BizTalk Server y la base de datos de BizTalk MessageBox, la base de datos de administración de BizTalk, las bases de datos BAM y otras bases de datos. En escenarios de carga elevada, esta comunicación, puede dar lugar a que el tráfico de red considerable y puede convertirse en un cuello de botella, especialmente cuando no se han optimizado configuración de red, no hay suficientes tarjetas de interfaz de red se instalan o no hay suficiente ancho de banda es está disponible.  
  
 En esta sección se ofrece algunas recomendaciones generales para mejorar el rendimiento de la red y describe varias entradas del registro que pueden modificarse para optimizar la pila de red para mitigar la aparición de cuellos de botella en la red.  
  
> [!IMPORTANT]  
>  Algunas de las recomendaciones de esta sección requieren modificaciones en el registro de Windows. El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de, restaurar y modificar el registro, vea el artículo de Microsoft Knowledge Base [256896, "Windows información del registro para los usuarios avanzados"](http://go.microsoft.com/fwlink/?LinkId=62729) (http://go.microsoft.com/fwlink/?LinkId=62729).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Directrices generales para mejorar el rendimiento de red](../technical-guides/general-guidelines-for-improving-network-performance.md)  
  
-   [Configuración que puede modificarse para mejorar el rendimiento de red](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento](../technical-guides/optimizing-performance.md)
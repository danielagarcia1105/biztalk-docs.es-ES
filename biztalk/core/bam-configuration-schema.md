---
title: Esquema de configuración de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], scaling
- scaling, BAM
- BAM, scaling
- configuration schema [BAM]
ms.assetid: 7eeeb07f-012e-44eb-a8b5-06e374946e2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0d73435dc0245c3c3ce2b1574aa5a70b468c60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230228"
---
# <a name="bam-configuration-schema"></a>Esquema de configuración de BAM
El esquema de configuración de BAM define un documento XML que contiene información acerca de su estructura, que utiliza la utilidad de administrador de BAM para la implementación. Puede implementar sus bases de datos en varios servidores para obtener escalabilidad. Para admitir esta escalabilidad, asegúrese de que la configuración del documento XML contiene los diferentes nombres de servidores y parámetros de configuración para las siguientes bases de datos:  
  
-   BAMPrimaryImport  
  
-   BAMStarSchema  
  
-   BAMAnalysis  
  
-   BAMArchive  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paquetes DTS de BAM](../core/bam-dts-packages.md)  
  
## <a name="see-also"></a>Vea también  
 [Cambiar la configuración de tiempo de ejecución BAM](../core/changing-bam-runtime-settings.md)
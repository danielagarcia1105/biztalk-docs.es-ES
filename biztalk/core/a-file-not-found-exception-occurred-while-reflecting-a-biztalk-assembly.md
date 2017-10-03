---
title: "Un archivo de excepción no encontrado al reflejar el ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f13e4539fca9a14e7827afcb092af76e03f8acc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a>Excepción de archivo no encontrado al reflejar el ensamblado de BizTalk
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Excepción de archivo no encontrado al reflejar el ensamblado de BizTalk "{0}". El problema surge si una o más dependencias no están disponibles. Para corregir este problema, pruebe una de las siguientes acciones: 1. Copie las dependencias del ensamblado en la misma carpeta. 2. Instale las dependencias que faltan en la memoria caché global de ensamblados.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el ensamblado de BizTalk que se publica hace referencia a otro ensamblado que no está en la memoria caché global de ensamblados (GAC) o en el mismo directorio.  
  
## <a name="user-action"></a>Acción del usuario  
 Además de las acciones especificadas en el mensaje de error, mueva el ensamblado de referencia a la memora caché global de ensamblados o cópielo en la misma ubicación que el ensamblado de BizTalk.  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione  **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** y, a continuación, haga clic en  **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** .  
  
2.  Abra un símbolo del sistema.  
  
3.  Vaya a la ubicación del ensamblado y escriba **gacutil /I /\<***nombre de ensamblado***> .dll**
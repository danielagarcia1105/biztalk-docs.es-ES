---
title: Error al cargar el ensamblado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13be3acf6974565c86cc87b14ed58929553d5220
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-loading-assembly"></a>Error al cargar el ensamblado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red. Compruebe la directiva de seguridad de acceso a código de la zona. O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk. Compruebe el ensamblado para el [ensamblado: ensamblado de BizTalk] atributo personalizado. O bien, es posible que el archivo no sea un ensamblado .NET. Si se trata de un archivo .dll o .exe, puede haber código no controlado.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red. Compruebe la directiva de seguridad de acceso a código de la zona. O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk. Compruebe el ensamblado para el [*ensamblado: ensamblado de BizTalk*] atributo personalizado. O bien, es posible que el archivo no sea un ensamblado .NET. Si el archivo es una DLL o exe, puede ser código no administrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Conceda el nivel de total confianza a la ubicación si es de un origen confiable.  Asegúrese de que el dll es un ensamblado .net de BizTalk válido.
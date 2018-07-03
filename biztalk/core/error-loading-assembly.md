---
title: Error al cargar el ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df561b964faa0fae80f41f1423d3034466bbb8ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994957"
---
# <a name="error-loading-assembly"></a>Error al cargar el ensamblado
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                          |
| Versión del producto |                                                                                                                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                                      |
|    Identificador del evento     |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  Origen del evento   |                                                                                                                                                                                  0                                                                                                                                                                                   |
|    Componente    |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  Nombre simbólico  |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  Texto del mensaje   | Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red. Compruebe la directiva de seguridad de acceso a código de la zona. O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk. Compruebe el ensamblado para el [ensamblado: ensamblado de BizTalk] atributo personalizado. O bien, es posible que el archivo no sea un ensamblado .NET. Si se trata de un archivo .dll o .exe, puede haber código no controlado. |
  
## <a name="explanation"></a>Explicación  
 Este error indica que es posible que la ubicación no sea de total confianza si está en un recurso compartido de red. Compruebe la directiva de seguridad de acceso a código de la zona. O bien, es posible que el archivo no sea un ensamblado .NET de Biztalk. Compruebe el ensamblado para el [*ensamblado: ensamblado de BizTalk*] atributo personalizado. O bien, es posible que el archivo no sea un ensamblado .NET. Si el archivo es una DLL o exe, puede ser código no administrado.  
  
## <a name="user-action"></a>Acción del usuario  
 Conceda el nivel de total confianza a la ubicación si es de un origen confiable.  Asegúrese de que el dll es un ensamblado .net de BizTalk válido.
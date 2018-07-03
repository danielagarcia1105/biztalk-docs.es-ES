---
title: Un archivo de excepción no encontrado al reflejar el ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee0cffc331765924b4fe7d29d95f7094b14aecb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000845"
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a>Excepción de archivo no encontrado al reflejar el ensamblado de BizTalk
## <a name="details"></a>Detalles  

|                 |                                                                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                           |
| Versión del producto |                                                                                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                       |
|    Identificador del evento     |                                                                                                                                                                   0                                                                                                                                                                    |
|  Origen del evento   |                                                                                                                                                                   0                                                                                                                                                                    |
|    Componente    |                                                                                                                                                                   0                                                                                                                                                                    |
|  Nombre simbólico  |                                                                                                                                                                   0                                                                                                                                                                    |
|  Texto del mensaje   | Un archivo de excepción no encontrado al reflejar el ensamblado de BizTalk "{0}". El problema surge si una o más dependencias no están disponibles. Para corregir este problema, pruebe uno de los siguientes: 1. Copie las dependencias del ensamblado en la misma carpeta. 2. Instale las dependencias que faltan en la memoria caché global de ensamblados. |

## <a name="explanation"></a>Explicación  
 Este error indica que el ensamblado de BizTalk que se publica hace referencia a otro ensamblado que no está en la memoria caché global de ensamblados (GAC) o en el mismo directorio.  

## <a name="user-action"></a>Acción del usuario  
 Además de las acciones especificadas en el mensaje de error, mueva el ensamblado de referencia a la memora caché global de ensamblados o cópielo en la misma ubicación que el ensamblado de BizTalk.  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Visual Studio**y, a continuación, haga clic en **Visual Studio**.  

2. Abra un símbolo del sistema.  

3. Vaya a la ubicación del ensamblado y escriba **gacutil /I /\<**<em>nombre del ensamblado</em>**\>.dll**

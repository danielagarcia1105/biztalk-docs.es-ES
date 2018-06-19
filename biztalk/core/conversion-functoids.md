---
title: Functoids de conversión | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cd7abcf-f524-4e85-b8d5-d6123767490f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 192db4b03f80674f2eb90be2255a8682454bde2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237892"
---
# <a name="conversion-functoids"></a>Functoids de conversión

## <a name="overview"></a>Información general
**Conversión** functoids se utilizan para realizar conversiones entre números y sus equivalentes ASCII y para convertir números de base 10 en su base 8 y 16 equivalentes de base.  
  
 Todos los functoids de conversión toman un único parámetro de entrada.  
  
> [!NOTE]
>  Debido a cambios en el sistema de tipos subyacente, el **conversión** functoids en esta versión del asignador de BizTalk producen resultados ligeramente diferentes de los que se obtenían en las versiones anteriores. Por ejemplo, en versiones anteriores del asignador de BizTalk un valor de entrada de -20 a la **Hexadecimal** functoid daba como resultado 0xffec. En esta versión, el mismo valor de -20 dará como resultado 0xFFFFFFEC.  

## <a name="available-functoids"></a>Functoids disponibles  
 El **conversión** functoids son: 

* ASCII a carácter
* Carácter a ASCII
* Hexadecimal
* Octal

Se describen estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 

## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids básicos a un mapa](../core/how-to-add-basic-functoids-to-a-map.md)   

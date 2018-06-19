---
title: Se encontró el número de control duplicados de conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe63d3814bcce178164054ab8dcf673eeb4f395a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278564"
---
# <a name="transaction-set-duplicate-control-number-found"></a>Se ha encontrado un número de control de conjunto de transacciones duplicado
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12TsDuplicateNumberFoundDescription|  
|Texto del mensaje|Se ha encontrado un número de control de conjunto de transacciones duplicado|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque el número de control del conjunto de transacciones para un conjunto de transacciones de un grupo de dicho intercambio era el mismo que el número de control para otro conjunto de transacciones de dicho grupo.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Cambie los números de control de conjunto de transacciones de los conjuntos de transacciones en el intercambio de entrada de modo que no haya números de control duplicados para los conjuntos de transacciones de un grupo.  
  
-   Deshabilite la comprobación de números de control duplicados para conjuntos de transacciones según se indica a continuación:  
  
    1.  Abra la consola de administración de BizTalk Server.  
  
    2.  Abra el cuadro de diálogo Propiedades de EDI correspondiente a la entidad que envió el intercambio.  
  
    3.  Para intercambios X12, desactive "Comprobar si hay duplicado de Número de control de conjunto de transacciones (ST2) en el grupo" en la página Propiedades de procesamiento de intercambio X12 del cuadro de diálogo Propiedades de EDI.  
  
    4.  Para intercambios EDIFACT, desactive "Comprobar si hay duplicado de Número de control de conjunto de transacciones (UNH1) en el grupo" en la página Propiedades de procesamiento de intercambio EDIFACT del cuadro de diálogo Propiedades de EDI.
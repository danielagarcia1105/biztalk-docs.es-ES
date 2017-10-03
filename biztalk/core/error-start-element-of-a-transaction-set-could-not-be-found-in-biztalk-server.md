---
title: "Detectado un error tras procesar conjuntos de transacciones porque no se encontró el elemento de inicio de un conjunto de transacciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b08046d1733aa8426909d7dddac4b10e48c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a>Se detectó un error tras procesar conjuntos de transacciones porque no se encontró el elemento de inicio de un conjunto de transacciones
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|InvalidEfactBiboXmlFormat|  
|Texto del mensaje|Se detectó un error tras procesar {0} conjunto(s) de transacciones. No se pudo encontrar el elemento de inicio de un conjunto de transacciones.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción de EDI no pudo procesar un conjunto de transacciones entrante porque la canalización de recepción no encontró el encabezado ST o UNH.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, póngase en contacto con el remitente del intercambio y pídale que se asegure de que el conjunto de transacciones con error comience por un segmento ST01 o UNH 1.
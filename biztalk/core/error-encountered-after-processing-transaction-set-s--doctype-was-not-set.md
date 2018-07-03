---
title: Detectó un error tras procesar conjuntos de transacciones porque DocType sin está definir | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df010d497f61a14644c46f8b7f5cdfa183340615
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003381"
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a>Se detectó un error tras procesar conjunto(s) de transacciones porque DocType está sin definir
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                     DocTypeNotSet                                      |
|  Texto del mensaje   |     Detectó un error tras procesar {0} conjuntos de transacciones. DocType sin definir.     |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar un conjunto de transacciones entrante porque ST01 (para intercambios X12) o UNH2.1 (para intercambios EDIFACT) no estaba configurado para el conjunto de transacciones.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe que el segmento ST01 o UNH1 para el conjunto de transacciones con error está configurado en un tipo de documento válido.
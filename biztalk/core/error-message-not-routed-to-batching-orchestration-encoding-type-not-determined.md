---
title: El mensaje no puede enrutarse a la orquestación por lotes no se pudo determinar el tipo de codificación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f23ccfc1b79e2fca4ece8e67370513723ac27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990189"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a>El mensaje no puede enrutarse a la orquestación de procesamiento por lotes. No se pudo determinar el tipo de codificación
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| Versión del producto |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    Identificador del evento     |                                                                                              -                                                                                              |
|  Origen del evento   |                                                   EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                    |
|    Componente    |                                                                                       Motor de procesamiento por lotes                                                                                       |
|  Nombre simbólico  |                                                                                     UnknownEncodingType                                                                                     |
|  Texto del mensaje   | El mensaje no puede enrutarse a la orquestación de procesamiento por lotes. No se pudo determinar el tipo de codificación. El tipo de codificación debe ser X12 o EDIFACT para que el mensaje pueda procesarse por lotes. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que un elemento de lote no EDI no se enrutó a la instancia de la orquestación por lotes, incluso aunque el conjunto de transacciones cumpla los criterios de filtro para su procesamiento por lotes. El conjunto de transacciones no se pudo enrutar a la instancia de la orquestación por lotes porque la propiedad de contexto EDI.EncodingType no se promocionó con el valor 0 para X12 o 1 para EDIFACT. Este error tuvo lugar cuando el componente de canalización BatchMarker enrutó el elemento de lote a la orquestación de enrutamiento, pero una asignación no convirtió el elemento de lote no EDI en un mensaje EDI. Como resultado, la orquestación de enrutamiento no pudo determinar el tipo de codificación a partir de los encabezados EDI.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que una asignación convierta el mensaje no EDI en un mensaje EDI antes de que se enrute a la orquestación de enrutamiento. También debe incluir un componente de canalización personalizado (con el componente BathMarker) o una orquestación personalizada para procesar el elemento de lote no EDI. Para obtener más información, consulte "Ensamblar un intercambio EDI por lotes" en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].
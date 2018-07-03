---
title: La actividad económica de BizTalk no se ha configurado para informar del estado de EDI / AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb2a6b9d6eaa6ac14f51c7f05e40a9f6ccffccd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010533"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a>La actividad económica de BizTalk no se ha configurado para informar del estado de EDI / AS2
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| Versión del producto |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    Identificador del evento     |                                                                      -                                                                      |
|  Origen del evento   |                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
|    Componente    |                                                                 Motor AS2                                                                  |
|  Nombre simbólico  |                                                                      -                                                                      |
|  Texto del mensaje   | Supervisión de la actividad económica (BAM) no se ha configurado para la generación de informes de estado de EDI/AS2. La característica de informes de estado se deshabilitará. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que no se habilitó la generación de informes de estado de EDI/AS2 porque Supervisión de la actividad económica (BAM) no se ha configurado a través del Asistente para configuración de BizTalk. La infraestructura de BAM es un requisito previo para la generación de informes de estado de EDI/AS2.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, ejecute el Asistente para configuración de BizTalk y configure Supervisión de la actividad económica.
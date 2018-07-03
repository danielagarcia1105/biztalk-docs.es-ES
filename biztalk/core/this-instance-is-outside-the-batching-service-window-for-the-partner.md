---
title: Esta instancia está fuera de la ventana de servicio de procesamiento por lotes para el socio comercial | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741439b5d6691a3218811568087450f2008b0ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966485"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a>Esta instancia está fuera de la ventana Servicio de procesamiento por lotes.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                    Motor de procesamiento por lotes                                     |
|  Nombre simbólico  |                              OutsideBatchingServiceWindow                              |
|  Texto del mensaje   |          Esta instancia está fuera de la ventana Servicio de procesamiento por lotes.          |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que no se pudo iniciar una instancia de la orquestación de procesamiento por lotes porque la instancia quedó fuera del intervalo de activación para la entidad.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, abra la página Configuración de creación de lotes de intercambio de las Propiedades de EDI para la entidad y asegúrese de que la instancia de la orquestación se encuentra dentro del intervalo de activación. Si no, cambie la propiedad de tiempo de inicio y, a continuación, haga clic en **iniciar**.
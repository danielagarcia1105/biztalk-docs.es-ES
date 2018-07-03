---
title: No hay ningún elemento por lotes para enviar y no se puede enviar un mensaje vacío porque no está configurado para entidad | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0752079a-173e-4de3-96f4-e5de01b799b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73d0d44c8a5a206748eb128cd2461d1d04b54c93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976669"
---
# <a name="there-are-no-batch-elements-to-send-and-an-empty-message-cannot-be-sent-as-it-is-not-configured-for-party"></a>No hay elementos por lotes que enviar, ni es posible enviar un mensaje vacío porque no está configurado para la entidad
## <a name="details"></a>Detalles  
  
|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| Versión del producto |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    Identificador del evento     |                                                       -                                                       |
|  Origen del evento   |            EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]             |
|    Componente    |                                                Motor de procesamiento por lotes                                                |
|  Nombre simbólico  |                                            EmptyMessageNotAllowed                                             |
|  Texto del mensaje   | No hay ningún elemento por lotes para enviar y no se puede enviar un mensaje vacío porque no está configurado para entidad {0} |
  
## <a name="explanation"></a>Explicación  
 Esta advertencia indica que no se envió ningún mensaje de lote en un proceso de procesamiento por lotes basado en programa porque no se recibió ningún elemento de lote cuando estaba programada la liberación del lote, y no se ha habilitado la señal de lotes vacíos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para impedir que se exponga esta advertencia, configure la señal de lotes vacíos mediante el siguiente procedimiento:  
  
1.  Abra la consola de administración de BizTalk Server.  
  
2.  Vaya al nodo Entidades.  
  
3.  Abra el cuadro de diálogo Propiedades de EDI para la entidad.  
  
4.  Haga clic en el nodo Configuración de creación de lotes de intercambio (para la codificación correspondiente).  
  
5.  Haga clic en el Programador.  
  
6.  Haga clic en la propiedad Enviar señal de lotes vacíos.
---
title: Error de creación del mensaje de Control para el identificador de lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba63bc570ac29f95c70b5bc6e09050e26c435b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979805"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a>Error en la creación del mensaje de control para el identificador del lote
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                               CreateControlMessageFailed                               |
|  Texto del mensaje   |                  Error en la creación del mensaje de control para el identificador {0} del lote.                  |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que BizTalk Server no pudo iniciar o detener un lote.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que esté presente un lote con el identificador dado en las propiedades del acuerdo contenedor y que la base de datos esté activa.
---
title: No se encontró el lote | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab810e4cfadc77c8fafe34b5cb78aaa417dfe5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015069"
---
# <a name="the-batch-was-not-found"></a>No se encontró el lote
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                   Err_BatchNotFound                                    |
|  Texto del mensaje   |                                No se encontró el lote.                                |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, indica que BizTalk Server no encontró un lote durante el inicio o detención de un lote mientras la orquestación por lotes intentaba procesar un mensaje por lotes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de el lote correspondiente esté presente en las propiedades del acuerdo contenedor.
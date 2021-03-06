---
title: Error al importar-copiar porque hay lotes activos pendientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74bfdccbd12db00cd0f325aedee2e42cc76729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970541"
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a>Error al importar-copiar porque hay lotes activos pendientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| Versión del producto |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    Identificador del evento     |                                                       -                                                        |
|  Origen del evento   |             EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]             |
|    Componente    |                                                   Motor EDI                                                   |
|  Nombre simbólico  |                                              Err_ActiveBatchFound                                              |
|  Texto del mensaje   | Error al importar o copiar porque hay lotes activos o pendientes. Detenga los lotes activos o pendientes e intente realizar de nuevo la importación o copia. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo importar un archivo de enlace o copiar la configuración, porque los acuerdos afectados tienen uno o varios lotes activos o pendientes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que todos los lotes de los acuerdos afectados se muestran como detenidos en las propiedades del acuerdo.
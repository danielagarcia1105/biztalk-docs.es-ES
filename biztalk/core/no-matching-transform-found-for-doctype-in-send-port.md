---
title: Se encontró ninguna transformación coincidente para DocType en puerto de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9668694f5cde2e99775d1392c8722bad0645b251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966213"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>No se ha encontrado ninguna transformación coincidente para DocType en Puerto de envío
## <a name="details"></a>Detalles  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| Versión del producto |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    Identificador del evento     |                                                   -                                                    |
|  Origen del evento   |         EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
|    Componente    |                                               Motor EDI                                               |
|  Nombre simbólico  |                             NoMatchingTransformFoundForSendPortAndDocType                              |
|  Texto del mensaje   | Se encontró ninguna transformación coincidente para DocType {0} en el puerto de envío {1}. Incoherente con la información de ExplorerOM |
  
## <a name="explanation"></a>Explicación  
 Este error indica que no se encontró ninguna transformación coincidente para un DocType y Puerto de envío.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, haga lo siguiente:  
  
1.  Abra la consola de administración de BizTalk, localice el transporte y haga clic con el botón secundario en el nombre del transporte.  
  
2.  Haga clic en **Propiedades**.  
  
3.  En la lista Tipo de puerto, seleccione el puerto correcto. Haga clic en **configurar**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de envío de [nombre de puerto], haga clic en **asignaciones de salida** en el panel izquierdo.  
  
5.  Compruebe que aquí aparece la asignación y que corresponde con el tipo de documento correcto.
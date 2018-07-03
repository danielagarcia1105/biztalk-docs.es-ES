---
title: Error al analizar. El X12 grupo funcional del intercambio contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2229c83-89bd-491f-9504-4afbf0084297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4175e4057dca49a3187ebf48e333170e06a1099
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982973"
---
# <a name="error-encountered-during-parsing-the-x12-functional-group-in-the-interchange-had-the-following-errors"></a>Error al analizar. El grupo funcional X12 del intercambio contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| Versión del producto |                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                         |
|    Identificador del evento     |                                                                                     -                                                                                     |
|  Origen del evento   |                                          EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
|    Componente    |                                                                                Motor EDI                                                                                 |
|  Nombre simbólico  |                                                                      X12FunctionalGroupReceiveError                                                                       |
|  Texto del mensaje   | Error al analizar. El X12 grupo funcional con Id. '{0}', en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI ha encontrado un error al analizar un intercambio X12 entrante debido a los errores indicados con el grupo funcional identificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el grupo y, a continuación, determine la resolución del problema en la ayuda del producto.
---
title: Error al analizar. El intercambio Edifact contenía los errores siguientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d891abe7ca75dbbe9052f221970e235b390269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988213"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a>Error al analizar. El intercambio Edifact contenía los errores siguientes
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| Versión del producto |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    Identificador del evento     |                                                                     -                                                                      |
|  Origen del evento   |                           EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
|    Componente    |                                                                 Motor EDI                                                                 |
|  Nombre simbólico  |                                                        EfactInterchangeReceiveError                                                        |
|  Texto del mensaje   | Error al analizar. El intercambio Edifact con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía los errores siguientes: |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI encontró un error al analizar un intercambio EDIFACT entrante debido a los errores indicados en el intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, use la información del mensaje de error para identificar el error en el intercambio y, a continuación, determine la resolución del problema en la ayuda del producto.
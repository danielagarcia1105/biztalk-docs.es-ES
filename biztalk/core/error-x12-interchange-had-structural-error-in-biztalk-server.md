---
title: 'El intercambio contenía un error estructural. Último grupo funcional con estructura válida fue el Id.: | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3da8a701e543fe5bfb9453af3cfa2514414f5c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988101"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>El intercambio contenía un error estructural. El Id. del último grupo funcional con estructura válida fue:
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| Versión del producto |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    Identificador del evento     |                                                                         -                                                                          |
|  Origen del evento   |                               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
|    Componente    |                                                                     Motor EDI                                                                     |
|  Nombre simbólico  |                                                     X12InterchangeStructuralErrorAfter1stGroup                                                     |
|  Texto del mensaje   | El intercambio con Id. '{0}', Id. de remitente '{1}', Id. de destinatario '{2}' contenía un error estructural. El Id. del último grupo funcional con estructura válida fue '{3}'. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio X12 entrante porque ha tenido lugar un error estructural en el intercambio después del grupo funcional indicado. Esto puede haberse producido con un intercambio que se estaba conservando, con conjuntos de transacciones suspendidos debido al error. Como resultado de este error, el o los conjuntos de transacciones que incluían el error se han suspendido, pero el resto de los conjuntos de transacciones se han procesado como parte del lote conservado.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que corrija el error estructural y vuelva a enviar el intercambio.
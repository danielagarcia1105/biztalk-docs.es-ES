---
title: Error de serialización Xml de intercambio X12 debido a una estructura no válida. Busca TransactionSet o GE, pero no se encuentra | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05608a6e38d90a9e18004fa650ee6d5f7911109c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977557"
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a>Error de serialización Xml de intercambio X12 debido a una estructura no válida. Se busca TransactionSet o GE, pero no se encuentra.
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| Versión del producto |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    Identificador del evento     |                                                         -                                                          |
|  Origen del evento   |               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
|    Componente    |                                                     Motor EDI                                                     |
|  Nombre simbólico  |                                           X12TransactionSetOrGeNotFound                                            |
|  Texto del mensaje   | Error de serialización Xml de intercambio X12 debido a una estructura no válida. Se busca TransactionSet o GE, pero no se encuentra. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo serializar el intercambio saliente porque la estructura del intercambio no era válida. El motivo podría ser que los encabezados o finalizadores requeridos no están presentes o no son válidos. Esto puede suceder si un conjunto de transacciones de un grupo no es seguido de otro conjunto de transacciones o del finalizador de grupo. También podría tener lugar si hay un error en las comprobaciones de integridad estructural.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe la estructura del intercambio, asegúrese de que los encabezados y finalizadores del grupo o del conjunto de transacciones son válidos y reenvíe el intercambio.
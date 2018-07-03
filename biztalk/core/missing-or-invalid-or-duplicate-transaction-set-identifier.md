---
title: Identificador de conjunto de transacciones falta o no válido o duplicado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 476b510396d29d5f4e85a13ed7c3bca3ee3fcef3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971725"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a>El identificador de conjunto de transacciones falta, no es válido o está duplicado
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                      X12TsMissingOrInvalidTsIdentiferDescription2                      |
|  Texto del mensaje   |            Identificador de conjunto de transacciones falta o no válido o duplicado '{0}'            |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio X12 porque el valor del identificador del conjunto de transacciones (en el campo ST01) faltaba, estaba duplicado o contenía un valor no válido. Esto puede producirse si el esquema del documento no tiene un encabezado ST y un finalizador SE.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo ST01 y que el esquema tenga una entrada para el encabezado ST y el finalizador SE. Compruebe que el valor de ST01 es un designador de tipo de documento válido de tres dígitos. Compruebe que el campo ST01 no sea un duplicado del campo ST01 de otro conjunto de transacciones.
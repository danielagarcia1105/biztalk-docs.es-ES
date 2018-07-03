---
title: Identificador de conjunto de transacciones falta o no válidos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f0444468b7f7ff52b38bcd8db01a6bded5ed0a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009933"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a>El identificador del conjunto de transacciones falta o no es válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                     EfactTsMissingOrInvalidTsIdentiferDescription                      |
|  Texto del mensaje   |                     El identificador del conjunto de transacciones falta o no es válido                      |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o de envío no pudo procesar el intercambio EDIFACT porque el valor del identificador del conjunto de transacciones (en el campo UNH2.1) faltaba o contenía un valor no válido.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el intercambio tenga un valor para el campo UNH2.1. Compruebe que el valor de UNH2.1 es un designador de tipo de documento válido de uno o seis dígitos.
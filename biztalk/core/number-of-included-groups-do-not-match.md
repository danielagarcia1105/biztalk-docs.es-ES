---
title: Número de grupos incluidos no coincide. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f02262012a5d02cebaf86fae5a4d19d9b5486d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263036"
---
# <a name="number-of-included-groups-do-not-match"></a>El número de grupos incluidos no coincide
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12Ta1InvalidNumberOfIncludedGroupsDescription|  
|Texto del mensaje|Número de incluye grupos no coinciden|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que el número de grupos del intercambio no es igual al número del finalizador de intercambio (campo IEA01). Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error. (El mensaje de error no se envía si el intercambio se conserva y los conjuntos de transacciones se suspenden al producirse un error o bien si el intercambio se divide.)  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el número que aparece en el campo IEA01 del finalizador de intercambio es el mismo que el número de grupos del intercambio y vuelva a enviar el intercambio.
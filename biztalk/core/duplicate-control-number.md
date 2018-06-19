---
title: Número de Control duplicado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e83f685242f4c69e6a142f3abb027017657611f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239612"
---
# <a name="duplicate-control-number"></a>Número de control duplicado.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Número de control duplicado.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar un intercambio entrante porque tenía el mismo número de control de intercambio, grupo o conjunto de transacciones que un intercambio recibido previamente. Esto provocará un error siempre que estén habilitadas las correspondientes comprobaciones de números de control duplicados.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Asegúrese de que el intercambio enviado a BizTalk Server no tiene el mismo número de control de intercambio, grupo o conjunto de transacciones que un intercambio previo, si está habilitada la correspondiente comprobación de número de control duplicado.  
  
-   Deshabilitar la comprobación de número de control duplicados. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], haga clic con el botón secundario en la entidad correspondiente y abra el cuadro de diálogo Propiedades de procesamiento de intercambio EDIFACT o bien Propiedades de procesamiento de intercambio X12 para la entidad como remitente del intercambio. Para deshabilitar una comprobación para un intercambio EDIFACT, desactive la propiedad Comprobar si hay duplicado de UNB5 (número de control de intercambio), Comprobar si hay duplicado de Número de control de grupo (UNG5) en el intercambio o Comprobar si hay duplicado de Número de control de conjunto de transacciones (UNH1) en el grupo. Para deshabilitar una comprobación para un intercambio X12, desactive la propiedad Comprobar si hay duplicado de número de control de intercambio (ISA13), Comprobar si hay duplicado de Número de control de grupo (GS6) en el intercambio o Comprobar si hay duplicado de Número de control de conjunto de transacciones (ST2) en el grupo.
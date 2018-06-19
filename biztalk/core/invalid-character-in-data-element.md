---
title: Carácter no válido en el elemento de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db7e2c72-f2cc-4157-aa26-062d2cc1210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc805fbede667013b56088b3d2c29913157c2fe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257116"
---
# <a name="invalid-character-in-data-element"></a>Carácter no válido en el elemento de datos.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12DeInvalidCharacterInDataElementDescription|  
|Texto del mensaje|Carácter no válido en el elemento de datos.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque un valor de un elemento de datos no se ajustaba al valor especificado en el esquema EDI.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor del elemento de datos se ajusta al esquema EDI y vuelva a enviar el intercambio.
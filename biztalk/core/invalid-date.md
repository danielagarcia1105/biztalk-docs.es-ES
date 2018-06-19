---
title: Fecha no válida | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41da9c5-9dcf-44cd-be5b-922e6c267ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259456e781f5f5255f9fed8a51c8eb0569dd57b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257396"
---
# <a name="invalid-date"></a>Fecha no válida.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12DeInvalidDateDescription|  
|Texto del mensaje|Fecha no válida.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante o que la canalización de envío no pudo procesar el intercambio saliente porque un valor de fecha en un elemento de datos no se ajustaba al tipo de datos que especifica el esquema EDI o el valor de fecha en el encabezado del campo GS04 en un intercambio X12 no se ajustaba al esquema de servicio (X12ServiceSchema en BaseArtifacts.dll). Para X12, el esquema de servicio define una fecha en el campo GS04 según el tipo de datos X12_DT y de entre seis y ocho caracteres de longitud.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, asegúrese de que el valor de hora en un elemento de datos se ajusta al tipo de datos que especifica el esquema EDI o el valor de fecha en el encabezado GS04 de un intercambio X12 se ajusta al esquema de servicio y vuelva a enviar el intercambio.
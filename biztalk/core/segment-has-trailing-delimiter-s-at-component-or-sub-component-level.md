---
title: El segmento contiene delimitadores finales en el componente o subcomponente nivel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eede2923da1ed206a897b879b7b6be589800e4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269668"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a>El segmento tiene uno o más delimitadores finales en el nivel de componente o subcomponente.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|X12SeSegmentHasTrailingDelimiterDescription|  
|Texto del mensaje|El segmento tiene uno o más delimitadores finales en el nivel de componente o subcomponente.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante porque el intercambio contenía delimitadores finales y estos no están habilitados para la entidad como remitente del intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, habilite los separadores finales tal como se indica a continuación:  
  
1.  Abra la consola de administración de BizTalk Server, vaya a la carpeta Entidades y abra las Propiedades de EDI para la entidad.  
  
2.  Vaya a la página Validación y generación de confirmación para X12 o EDIFACT, según corresponda.  
  
3.  Haga clic en "Permitir separadores finales".
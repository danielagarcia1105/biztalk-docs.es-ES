---
title: Los delimitadores no son únicos, campo y el separador de componentes son los mismos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cba15b30-b07d-4caa-8c43-6b4d8c4ca81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f803612a905f0be196afcfc0b43af23501ccdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238556"
---
# <a name="delimiters-are-not-unique-field-and-component-separator-are-the-same"></a>Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Los delimitadores no son únicos. Los separadores de campo y de componente coinciden.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío EDI no pudo procesar un intercambio saliente porque el elemento de datos y los separadores de componentes tenían el mismo valor. En un intercambio X12, el separador del elemento de datos es el carácter de la cuarta posición de carácter del segmento ISA y el separador de componente es el carácter del campo ISA16. En un intercambio EDIFACT, el separador del elemento de datos es el carácter del campo UNA2 y el separador de componente es el carácter del campo UNA1. Dos separadores con el mismo valor pueden tener lugar (pero provocarán una condición de error) en un escenario de lote conservado o si se recibe un intercambio mediante una transmisión de atravesar y posteriormente el puerto de envío lo recoge como archivo XML en el cuadro de mensajes.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie el valor del elemento de datos o de los separadores de componentes y, a continuación, vuelva a enviar el intercambio.
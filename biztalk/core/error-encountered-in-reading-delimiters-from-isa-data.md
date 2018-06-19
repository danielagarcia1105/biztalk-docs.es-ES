---
title: Error al leer los delimitadores de los datos ISA | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fcde2519740adc5531363911146164f460f9b3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240164"
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a>Error al leer los delimitadores de los datos ISA.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|InvalidIsaData|  
|Texto del mensaje|Error al leer los delimitadores de los datos ISA.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI encontró un error al procesar un intercambio X12 entrante porque no pudo analizar los separadores del segmento ISA.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, compruebe que los separadores del segmento ISA del intercambio entrante son únicos y válidos. Si no es así, pida al remitente del intercambio que especifique valores únicos y válidos en cada uno de los campos separadores (el segmento ISA11 para el separador de repetición y el segmento ISA16 para el separador de componente) y reenvíe el intercambio.
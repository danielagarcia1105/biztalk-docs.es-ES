---
title: "Error durante la generación de instancias: campo puede repetirse, pero no se ha definido el delimitador de repetición | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 366caec69fd84b91cf815a58e4975e8e5d7b4d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a>Error detectado durante la generación de instancias: el campo puede repetirse, pero el delimitador de repeticiones no se ha definido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor EDI|  
|Nombre simbólico|-|  
|Texto del mensaje|Error detectado durante la generación de instancias. El campo {0} puede repetirse, pero el delimitador de repeticiones no se ha definido.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que BizTalk Server no pudo generar una instancia de mensaje X12 porque el campo indicado se puede repetir (según especifica el esquema) pero no se ha definido ningún separador de repetición. Esto tiene lugar cuando un campo del esquema tiene minOccurs igual o superior a 1, pero se ha definido un identificador estándar en lugar de un separador de repetición. (Para intercambios EDIFACT, de manera predeterminada se define un separador de repetición).  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, seleccione un separador de repetición en lugar de un identificador estándar para ISA11 en la página Definición de segmento ISA para la entidad como receptor de intercambio y especifique un carácter como separador. Si no se ha resuelto ninguna entidad para el intercambio, defina el separador de repetición en la página Definición de segmento ISA de las propiedades globales (para intercambios X12).
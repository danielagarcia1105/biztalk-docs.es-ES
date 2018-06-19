---
title: Vocabularios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, vocabularies
- vocabularies, about vocabularies
- vocabularies
- Business Rules Engine, vocabularies
ms.assetid: 591673a0-2c4d-41ca-9997-b363c086dd66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9e20dfead51d54822d3316c8819d04a259cfa83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288012"
---
# <a name="vocabularies"></a>Vocabularios
Los términos usados para definir condiciones y acciones de reglas se expresan normalmente con una nomenclatura específica del dominio o del sector. Por ejemplo, un usuario de correo electrónico escribe reglas en términos de mensajes "recibidos de" y mensajes "recibidos después de", mientras que un analista de seguros escribe reglas en términos de "factores de riesgo" e "importe de cobertura".  
  
 Subyacentes a esta terminología específica del dominio se encuentran los artefactos tecnológicos (objetos, tablas de base de datos y documentos XML) que implementan condiciones y acciones de reglas. Vocabulariesare diseñado para salvar la brecha entre la semántica del negocio y la implementación.  
  
 Por ejemplo, un enlace de datos para un estado de aprobación puede apuntar a una determinada columna en una determinada fila de una determinada base de datos, representada como una consulta SQL. En lugar de insertar este tipo de representación compleja de una regla, puede crear una definición de vocabulario asociada con ese enlace de datos, con un nombre descriptivo de "Estado". A continuación, puede incluir "Estado" en cualquier número de reglas y el motor de reglas puede recuperar los datos correspondientes de la tabla.  
  
 A *vocabulario* es una colección de definiciones que consta de nombres descriptivos de hechos utilizados en condiciones de regla y las acciones. Las definiciones de vocabulario facilitan la lectura, la comprensión y el compartimiento de reglas entre personas de un dominio empresarial concreto.  
  
 Puede usar el Compositor de reglas de negocio para definir vocabularios que se ponen después en el almacén de reglas compartidas. También pueden usar vocabularios los programadores de herramientas responsables de integrar la creación de reglas en aplicaciones nuevas o existentes.  
  
 Para poder usar un vocabulario, se le debe poner la versión y se debe publicar en el almacén de reglas. Esto es para garantizar que las definiciones del vocabulario no cambiarán y para mantener la integridad referencial. Esto significa que las directivas que usan una versión concreta del vocabulario no darán errores de forma inesperada debido a cambios en el vocabulario subyacente.  
  
## <a name="see-also"></a>Vea también  
 [Motor de reglas de negocios](../core/business-rules-engine.md)
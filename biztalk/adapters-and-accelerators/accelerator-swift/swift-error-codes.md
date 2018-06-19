---
title: Códigos de error SWIFT de BizTalk Server | Documentos de Microsoft
description: Ver los tipos de clase y de validación para el Acelerador para SWIFT de BizTalk Server
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d8e027eb9cce1cf66342484070310141e10b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215028"
---
# <a name="swift-error-codes"></a>Códigos de Error SWIFT
SWIFT define muchas validaciones impuesta por la red con el conjunto de mensajes financieros (FIN). Cada validación relacionada con un tipo de comprobación con el contenido del mensaje y está asociado con un código de error de tres caracteres. El primer carácter del código de error implica la clase del problema detectado y es una letra. Los dos caracteres restantes indican los detalles del error (cuando se combina con la clase) y siempre se muestran como un código de dos dígitos.  

## <a name="class-of-errors"></a>Clase de errores  
 En la tabla siguiente se enumera las designaciones de letras, el tipo de validación, cambio de la regla asociada a cada clase de error, y si no se admite la clase de error.  
  
|Clase|Cambio de tipo y la regla de validación|¿Admitido?|  
|-----------|-------------------------------------|----------------|  
|**C, D, E**|Reglas de validación semántica 299 0|Admitida|  
|**Knn**|Clave no válida en el campo*nn*|Admitida|  
|**M50**|Ha superado la longitud de mensaje|No compatible|  
|**M60**|Se encontró un carácter no SWIFT|Admitida|  
|**T**|Códigos de error de validación de texto|Admitida|  
|**G**|Códigos de error específicos para las reglas Textval de grupo (TAZA) de usuario de mensaje|No compatible|  
|**B**|Códigos de error especial para servicios de valor agregado|No compatible|  
  
 Todos los errores SWIFT deben indicarse en el *manual de usuario de SWIFT*. Para obtener más información y para obtener una lista completa de códigos de error SWIFT, hacen referencia a la *reglas de validación de formato de mensaje* volumen de la *manual de usuario de SWIFT*. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]implementa las reglas en la edición de septiembre de 2003 de esta publicación. Se puede acceder al sitio Web de SWIFT en [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).  

## <a name="validation-errors"></a>Errores de validación  
 Hay algunos códigos que se definen de A4SWIFT. Estos códigos de error se utilizan en las reglas de validación o de la red creó e implementada por A4SWIFT, así que no hay ningún código de error correspondiente definido por SWIFT para dichas normas. Tabla siguiente muestra el código de error y el caso correspondiente en el que se produce el error. es el campo concreto que produce el error.  
  
|Código de error|Description|  
|----------------|-----------------|  
|A4SWIFT001|No puede ser el primer carácter del campo multilínea ':' o '-' carácter para las líneas segunda y posteriores.|  
|A4SWIFT002|Campo contiene un valor no válido.|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]incluye compatibilidad con algunos mensajes heredados, dado que las aplicaciones internas pueden usar estos mensajes. Por lo tanto, A4SWIFT mantiene las reglas SWIFT asociadas y los códigos de error.

## <a name="more-good-info"></a>Más información válida
[Solución de problemas: Problemas y soluciones](troubleshooting-issues-and-resolutions1.md)  
[Problemas conocidos](known-issues5.md)  
[Términos y definiciones comunes](glossary6.md)
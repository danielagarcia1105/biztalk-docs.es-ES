---
title: Convenciones de nomenclatura de esquema SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb792fe66e5806a186b0ffb946aa99f86a6a10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schema-naming-conventions"></a>Convenciones de nomenclatura de esquema SWIFT
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye los esquemas para la sociedad para los mensajes FIN de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo que se crearon con el Editor de BizTalk. Estos esquemas son compatibles con las siguientes convenciones a lo largo de:  
  
> [!NOTE]
>  Todos los esquemas son con control de versiones. Para ver la versión, abra [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y haga clic en el esquema en el Explorador de soluciones. Con el \<esquema > nodo seleccionado en el Editor de BizTalk, en el panel Propiedades, desplácese a la propiedad versión estándar.  
  
-   El nombre de cada archivo de esquema de intercambio es  **MT*xxx*.xsd **, donde *xxx* es el tipo de mensaje FIN.  
  
-   Es el nombre del archivo de directiva principal asociado para cada mensaje  **MT*xxx*_Master_Policy.xml**, y el nombre correspondiente en el motor de reglas de negocios (BRE) es   **MT*xxx*_Master_Policy**, con un nombre de la lista de  **MT*xxx*_PolicyList **.  
  
-   Es el nombre del archivo de directiva de validación asociados para cada mensaje  **MT*xxx*_Validation_Policy.xml**, y es el nombre correspondiente en el BRE  **MT* xxx*_Validation_Policy**.  
  
-   Dentro de cada esquema de mensaje, el nombre de la raíz es  **SWIFT_CATEGORY*z*_MT*zxx*_Interchange **, donde *z* es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.  
  
-   El espacio de nombres de destino para cada esquema de mensaje  **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx***, donde *z* es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.  
  
-   El tipo de documento es  **MT*zxx***, donde *zxx* es el tipo de mensaje.  
  
-   Los nombres de campos que no se numeran y subcampos incluyen nombres descriptivos empresariales. Se pone en mayúsculas la primera letra de cada palabra y los nombres no incluyen un espacio intermedio o signos de puntuación entre las palabras (por ejemplo, el nombre sería **ServiceIdentifier**, no **identificador del servicio de**) .  
  
-   Las etiquetas de secuencias dentro de los mensajes se ajustan a la *Guía de referencia de SWIFT* (por ejemplo, **SequenceA**).  
  
-   Las etiquetas de numeran SWIFT campos incluyen un título descriptivo seguido de la secuencia (si está presente), seguido por el código de número y el formato de letra opcional (por ejemplo, **Reference_A_20C**).  
  
-   Si hay una selección de varios formatos para un campo, la etiqueta del nodo es  **\<* elección*> **, y, a continuación, cada opción es un campo de número (por ejemplo, **Date_A_98A** y **DateTime_A_98C**).  
  
-   El nombre de la definición de elemento de nivel más bajo de un subcampo consta del nombre del campo secundario seguido **tipo** (por ejemplo, **accountType** de cuenta).  
  
 Otros espacios de nombres en el esquema de mensaje son los siguientes:  
  
-   xmlns: xs = "http://www.w3.org/2001/XMLSchema". Este es el espacio de nombres de esquema XML de W3C de forma predeterminada.  
  
-   xmlns: b = "http://schemas.microsoft.com/BizTalk/2003". Este es el espacio de nombres de BizTalk de forma predeterminada.  
  
 Cada esquema de mensaje directamente hace referencia al tipo base y los esquemas de tipo de datos comunes.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
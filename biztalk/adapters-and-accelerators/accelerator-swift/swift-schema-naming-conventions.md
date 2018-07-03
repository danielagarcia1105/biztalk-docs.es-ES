---
title: Convenciones de nomenclatura de esquemas de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabd9796497bdd5b81d34f71c01124f26de203d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987429"
---
# <a name="swift-schema-naming-conventions"></a>Convenciones de nomenclatura de esquemas de SWIFT
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] incluye los esquemas para la sociedad para los mensajes FIN de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo que se crearon con el Editor de BizTalk. Estos esquemas son compatibles con las siguientes convenciones a lo largo de:  
  
> [!NOTE]
>  Todos los esquemas tienen versiones. Para ver la versión, abra [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y haga clic en el esquema en el Explorador de soluciones. Con el \<esquema\> nodo seleccionado en el Editor de BizTalk, en el panel Propiedades, desplácese a la propiedad versión estándar.  
  
- El nombre de cada archivo de esquema de intercambio es **MT*xxx*.xsd**, donde *xxx* es el tipo de mensaje FIN.  
  
- Es el nombre del archivo de directiva principal asociado para cada mensaje **MT*xxx*_Master_Policy.xml**, y es el nombre correspondiente en el motor de reglas de negocios (BRE) **MT*xxx* _Master_Policy**, con un nombre de la lista de **MT*xxx*_PolicyList**.  
  
- Es el nombre del archivo de directiva de validación asociado para cada mensaje **MT*xxx*_Validation_Policy.xml**, y es el nombre correspondiente en el BRE **MT*xxx*_Validation_Policy**.  
  
- Dentro de cada esquema de mensaje, el nombre de la raíz es **SWIFT_CATEGORY*z*_MT*zxx*_Interchange**, donde *z* es el (categoría de mensaje primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.  
  
- El espacio de nombres de destino para cada esquema de mensaje **<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>** <em>, donde * z</em> es la categoría de mensaje (primer dígito del tipo de mensaje) y *zxx* es el tipo de mensaje.  
  
- El tipo de documento es **MT * zxx**<em>, donde * zxx</em> es el tipo de mensaje.  
  
- Los nombres de campos que no están numerados y campos secundarios incluyen nombres descriptivos empresariales. Se convierte en mayúsculas la primera letra de cada palabra y los nombres no incluyen un espacio intermedio o signos de puntuación entre palabras (por ejemplo, el nombre sería **ServiceIdentifier**, no **identificador del servicio**) .  
  
- Las etiquetas de secuencias dentro de los mensajes se ajustan a la *Guía de referencia de SWIFT* (por ejemplo, **SequenceA**).  
  
- Las etiquetas de numeran SWIFT campos incluyen un título descriptivo seguido de la secuencia (si existe), seguido por el código de número y el formato de letra opcional (por ejemplo, **Reference_A_20C**).  
  
- Donde hay una opción de varios formatos para un campo, la etiqueta del nodo es  **\< *elección*\>**, y, a continuación, cada opción es un campo de número (por ejemplo, **fecha _A_98A** y **DateTime_A_98C**).  
  
- El nombre de la definición de elemento de nivel más bajo de un subcampo consta del nombre del campo secundario seguido **tipo** (por ejemplo, **accountType** de cuenta).  
  
  Otros espacios de nombres en el esquema de mensaje incluyen lo siguiente:  
  
- xmlns: xs = "<http://www.w3.org/2001/XMLSchema>". Este es el espacio de nombres del esquema XML de W3C de forma predeterminada.  
  
- xmlns: b = "<http://schemas.microsoft.com/BizTalk/2003>". Este es el espacio de nombres de BizTalk predeterminado.  
  
  Cada esquema de mensaje directamente hace referencia al tipo base y los esquemas de tipo de datos comunes.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)
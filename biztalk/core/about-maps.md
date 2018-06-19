---
title: Acerca de las asignaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d15f37dc0ff0112906a449e1b1d84704b21727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225564"
---
# <a name="about-maps"></a>Acerca de las asignaciones
Con el Asignador de BizTalk, se define la relación entre un esquema de origen y uno de destino mediante vínculos y functoids. Un vínculo define una copia de datos directa de un registro o campo. Los vínculos puede conectarse directamente con elementos del otro esquema, o pueden establecer conexiones con functoids. Los functoids llevan a cabo manipulaciones de datos más complejas, como:  
  
-   Sumar el valor de dos campos del esquema de origen y copiar el resultado en el esquema de destino.  
  
-   Convertir un carácter en su formato equivalente ASCII.  
  
-   Devolver el promedio de un campo de un registro de repetición y copiar el resultado en un campo del esquema de destino.  
  
 El Asignador de BizTalk almacena las asignaciones en un archivo con la extensión .btm. El archivo guarda información de diseño acerca de la asignación, las ubicaciones de los iconos que representan functoids, los vínculos entre elementos de esquema y functoids y otra información acerca de la asignación. Cuando genera o compila la asignación, el Asignador de BizTalk convierte la información sobre la asignación en la hoja de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT).  
  
> [!NOTE]
>  El compilador de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiene un límite de 16 megabytes en el tamaño total de todas las cadenas en un único proyecto. Al compilar proyectos de BizTalk, el compilador serializa esquemas, asignaciones y orquestaciones para crear los ensamblados y, por ello, el tamaño total de todas las cadenas aumenta y puede superar el límite. Para resolver este problema, puede reorganizar el proyecto colocando esquemas y/o asignaciones en otros proyectos de Biztalk (normalmente, bajo la misma solución), de modo que el tamaño total de todas las cadenas de cada proyecto no supere los 16 MB.  
  
 Las asignaciones que cree pueden transformar o traducir datos y pueden ser específicas para un único socio comercial o utilizarse con muchos socios comerciales. En los temas de esta sección se proporciona una introducción a los conceptos relacionados con los esquemas de asignación. Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Vínculos en asignaciones](../core/links-in-maps.md)  
  
-   [Functoids en asignaciones](../core/functoids-in-maps.md)  
  
-   [Compilación de la asignación y las pruebas](../core/map-compilation-and-testing.md)
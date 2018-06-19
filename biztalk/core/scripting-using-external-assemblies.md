---
title: Secuencias de comandos con ensamblados externos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269204"
---
# <a name="scripting-using-external-assemblies"></a>Secuencias de comandos que utilizan ensamblados externos
Las secuencias de comandos con ensamblados externos es la forma recomendada de usar las secuencias de comandos en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los ensamblados externos proporcionan varias ventajas:  
  
-   Facilidad para compartir código  
  
-   Mantenimiento más sencillo  
  
-   Depuración más fácil  
  
> [!NOTE]
>  Comprobar asignación se produce un error si la **secuencias de comandos** functoid usa un ensamblado externo que no está registrado en la GAC. Funciona si el ensamblado externo está en la misma carpeta bin que el ensamblado del proyecto actual (colocado después de la generación).  
  
 Volver a usar el script basta con configurar la **Script** propiedad de la **secuencias de comandos** functoid. Puesto que el script está almacenado fuera de la asignación, es posible modificar el script sin modificar la asignación. Y puede utilizar la totalidad de herramientas de depuración de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para asegurarse de que el script se ejecuta correctamente.  
  
> [!WARNING]
>  El código del ensamblado externo debe ser seguro para subprocesos. En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.  
  
 Para una función de ejemplo que se aloja en un ensamblado externo, vea [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).  
  
## <a name="see-also"></a>Vea también  
 [Secuencias de comandos de Functoid](../core/scripting-functoid.md)   
 [Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [Cómo configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md)
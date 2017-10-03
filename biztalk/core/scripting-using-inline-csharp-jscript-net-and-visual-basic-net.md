---
title: "Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68fe19b4616e23066603995b6403654fa3960789
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a>Secuencias de comandos que utilizan C#, JScript .NET y Visual Basic .NET en línea
Las secuencias de comandos en línea son convenientes para el código personalizado que es poco probable que utilice en otra parte de la aplicación.  
  
 BizTalk guarda las secuencias de comandos en línea en las hojas de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT) que definen la asignación. Debido a esto, las secuencias de comandos pueden utilizar el mismo espacio de nombres que cualquier otra secuencia de comandos de hojas de estilo XSLT. En la tabla siguiente se muestran los espacios de nombres disponibles.  
  
|Espacio de nombres|Description|  
|---------------|-----------------|  
|Sistema|La clase System.|  
|System.Collection|Las clases de colección.|  
|System.Text|Las clases de texto.|  
|System.Text.RegularExpressions|Las clases de expresiones regulares.|  
|System.Xml|Las clases XML principales.|  
|System.Xml.Xsl|Las clases XSLT.|  
|System.Xml.Xpath|Las clases XPath.|  
|Microsoft.VisualBasic|Las clases de secuencias de comandos de Visual Basic.|  
  
 Para obtener más información acerca de los espacios de nombres y tipos de datos, busque "uso de secuencias de comandos de hojas de estilo XSLT \<msxsl: script >" y "System.Xml.Xsl.XslCompiledTransform" en la colección de .NET Framework.  
  
> [!CAUTION]
>  Evite utilizar la misma firma de método más de una vez. Cuando varios functoids de secuencia de comandos tienen la misma firma de método, BizTalk selecciona la primera implementación y descarta las otras.  
  
 Además de ser útiles para las secuencias de comandos que sólo se utilizan una vez, las secuencias de comandos también son prácticas para declarar variables globales que van a utilizar una serie de secuencias de comandos. Por ejemplo, en una secuencia de comandos en línea C#, podría poner la siguiente línea de código fuera de cualquier clase.  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 Esto crea una **ArrayList**, `statusList`, que está disponible para todas las secuencias de comandos en el mapa.  
  
 Para una secuencia de comandos de ejemplo en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).  
  
## <a name="see-also"></a>Vea también  
 [Secuencias de comandos de Functoid](../core/scripting-functoid.md)   
 [Secuencias de comandos con ensamblados externos](../core/scripting-using-external-assemblies.md)   
 [Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [Cómo configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md)
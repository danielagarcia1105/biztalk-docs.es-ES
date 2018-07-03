---
title: Configuración de salida de la especificación XSLT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d55a8ddccb996f11315c8856797147083da9123
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998037"
---
# <a name="set-map-compilation-and-output-settings"></a>Establezca la compilación de la asignación y configuración de salida
Establecer las propiedades de asignación en el asignador de BizTalk. 

Mediante estas propiedades de mapa, puede establecer cómo se compilan los mapas, incluir o excluir una declaración XML y establecer la codificación. 

Este tema muestra cómo establecer estas propiedades en el mapa.

## <a name="set-the-map-level-compilation"></a>Establezca la compilación de nivel de asignación

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , elige el `XslTransform` o `XslCompiledTransform` clase para compilar las asignaciones. 

1. Abrir la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.  
3. Establecer el **uso de transformación XSL** propiedad: 

    | Opción | Descripción |
    | --- | --- |
    | No definido | Se utiliza la marca de registro para la configuración de XslTransform: <ul><li>instancias de host de 64 bits: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>las instancias de host de 32 bits y funcionalidad de asignación de prueba de Visual Studio: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | La propiedad de compilación de nivel de asignación se establece en `XslTransform` (comportamiento heredado) | 
    | False | La propiedad de compilación de nivel de asignación se establece en `XslCompiledTransform` | 

> [!NOTE]
> A partir de BizTalk Server 2013, se ha cambiado el comportamiento de compilación del asignador de `XslTransform` a `XslCompiledTransform`. El [el asignador de actualizaciones de significado para usted](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) entrada de blog proporciona una excelente explicación del comportamiento y el impacto potencial. 
> 
> A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede elegir qué clase se debe compilar las asignaciones. 
  
## <a name="include-or-exclude-an-xml-declaration"></a>Incluir o excluir una declaración XML  
Puede elegir si una declaración XML es la salida o no. 

1. Abrir la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.  
3. En la lista desplegable para la **omitir declaración XML** propiedad, seleccione **Sí** para omitir una declaración XML. Seleccione **No** no para omitir una declaración XML.  

Podría aparecer una declaración XML (si seleccionó **n**) similar al siguiente.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>Establecer la codificación de datos de instancia de salida  
La codificación proporciona al motor en tiempo de ejecución la información que necesita para determinar qué juego de caracteres utilizar cuando cree el resultado de salida de una asignación.  
   
1. Abrir la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.    
3.  En la lista desplegable para la **codificación XSLT** propiedad, seleccione el juego de caracteres desee usados para los datos de instancia de salida.  
  
## <a name="see-also"></a>Vea también  
 [Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md)   
 [El asignador de BizTalk](../core/using-biztalk-mapper.md)   
 [Tipos válidos de codificación XSLT en el Asignador de BizTalk](../core/valid-biztalk-mapper-xslt-encoding-types.md)
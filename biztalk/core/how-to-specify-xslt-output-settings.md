---
title: Opciones de salida de cómo especificar XSLT | Documentos de Microsoft
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
ms.openlocfilehash: e1aa3eea4c3f2f4696d3dc1fdf8109aeddec3ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255340"
---
# <a name="set-map-compilation-and-output-settings"></a>Establezca la compilación del mapa y opciones de salida
Establecer las propiedades de asignación en el asignador de BizTalk. 

Uso de estas propiedades de asignación, puede establecer cómo se compilan los mapas, incluir o excluir una declaración XML y el codificador del juego. 

En este tema se muestra cómo establecer estas propiedades en el mapa.

## <a name="set-the-map-level-compilation"></a>Establezca la compilación de nivel de asignación

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , elige el `XslTransform` o `XslCompiledTransform` clase para compilar las asignaciones. 

1. Abra la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.  
3. Establecer el **Use la opción Transformar XSL** propiedad: 

    | Opción | Description |
    | --- | --- |
    | No definido | Se utiliza la marca de registro para la configuración de XslTransform: <ul><li>instancias de host de 64 bits:`HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</li><li>instancias de host de 32 bits y la funcionalidad de mapas de prueba de Visual Studio:`HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</li></ul> | 
    | True | La propiedad de compilación de nivel de asignación se establece en `XslTransform` (comportamiento heredado) | 
    | False | La propiedad de compilación de nivel de asignación se establece en`XslCompiledTransform` | 

> [!NOTE] 
> A partir de BizTalk Server 2013, se cambió el comportamiento de compilación de asignador de `XslTransform` a `XslCompiledTransform`. El [el asignador de actualizaciones significado para usted](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) entrada de blog proporciona una explicación excelente del comportamiento y el impacto potencial. 
> 
> A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede elegir qué clase se debe compilar las asignaciones. 
  
## <a name="include-or-exclude-an-xml-declaration"></a>Incluir o excluir una declaración XML  
Puede elegir si una declaración XML es la salida o no. 

1. Abra la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.  
3. En la lista desplegable para la **omitir declaración XML** propiedad, seleccione **Sí** para omitir una declaración XML. Seleccione **No** no para omitir una declaración XML.  

Aparecerá una declaración XML (si seleccionó **n**) similar al siguiente.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a>Establecer la codificación de datos de instancia de salida  
La codificación proporciona al motor en tiempo de ejecución la información que necesita para determinar qué juego de caracteres utilizar cuando cree el resultado de salida de una asignación.  
   
1. Abra la asignación en la vista de cuadrícula.
2. Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.    
3.  En la lista desplegable para la **codificación XSLT** propiedad, seleccione el juego de caracteres desea usar para los datos de instancia de salida.  
  
## <a name="see-also"></a>Vea también  
 [Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md)   
 [Con el asignador de BizTalk](../core/using-biztalk-mapper.md)   
 [XSLT en el asignador de BizTalk válido tipos de codificación](../core/valid-biztalk-mapper-xslt-encoding-types.md)
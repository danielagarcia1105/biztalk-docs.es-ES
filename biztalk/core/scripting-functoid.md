---
title: Functoid de scripting | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b26223884bce626404586115da36ff7989ac13b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982357"
---
# <a name="scripting-functoid"></a>Secuencias de comandos (functoid)
El **Scripting** functoid le permite usar un script personalizado o código en tiempo de ejecución para realizar funciones de lo contrario, no está disponibles. Por ejemplo, puede llamar a un ensamblado .NET en tiempo de ejecución mediante la **Scripting** functoid y escribir sus propias funciones personalizadas.  
  
 El **Scripting** functoid es compatible con los siguientes idiomas:  
  
- C# .NET  
  
- JScript .NET  
  
- Visual Basic .NET  
  
- Transformación de lenguaje de hojas de estilo extensible (XSLT)  
  
- Plantillas de llamada de XSLT  
  
  Otra diferencia importante entre el representador actual **Scripting** functoid y en versiones anteriores es que la secuencia de comandos ya no necesita crear y almacenar en el functoid. En su lugar, puede crear la secuencia de comandos en un ensamblado .NET independiente y hacer referencia al ensamblado a través de la **Script** propiedad. Al tener la secuencia de comandos en un ensamblado distinto se puede utilizar la misma secuencia de comandos en más de una asignación. Además, es posible que pueda adquirir **Scripting** functoid ensamblados de otros fabricantes.  
  
  Puede usar **Scripting** functoids creados en versiones anteriores del asignador de BizTalk con la versión actual del asignador de BizTalk. Sin embargo, es necesario que migre primero los functoids. Para obtener más información sobre cómo migrar **Scripting** functoids, consulte [migrar Functoids](../core/migrating-functoids.md).  
  
  Cuando se agrega un **Scripting** functoid a una asignación, deberá configurar la secuencia de comandos que utiliza el functoid. Si selecciona un **Scripting** functoid, la **Script** propiedad está habilitada en el **propiedades** ventana. Si hace clic en el botón de puntos suspensivos (**...** ) botón para esta propiedad, el **configurar Functoid de script** abre el cuadro de diálogo. También puede hacer doble clic en el **Scripting** functoid.  
  
  La siguiente tabla muestra los campos de este cuadro de diálogo.  
  
|Campo de cuadro de diálogo Configurar functoid de script|Descripción|  
|---------------------------------------------------|-----------------|  
|**Seleccionar tipo de script**|Utilice este campo para seleccionar el tipo de script que va a utilizar en este **Scripting** functoid.<br /><br /> Valores:<br /><br /> -   **Ensamblado externo**. Use este valor si desea asociar el **Scripting** functoid con un ensamblado en la caché de ensamblados global (GAC). **Advertencia:** el código en el ensamblado externo debe ser seguro para subprocesos. En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.<br />-   **C# en línea**.  Use este valor si desea asociar el **Scripting** functoid con código C# en el **script en línea** búfer.<br />-   **JScript .NET en línea**. Use este valor si desea asociar el **Scripting** functoid de secuencia de comandos de JScript .NET en el **script en línea** búfer.<br />-   **En línea Visual Basic .NET**. Use este valor si desea asociar el **Scripting** functoid con código de Visual Basic .NET en el **script en línea** búfer.<br />-   **XSLT en línea**. Use este valor si desea asociar el **Scripting** functoid con XSLT en el **script en línea** búfer.<br />-   **Plantilla de llamada XSLT en línea**. Use este valor si desea asociar el **Scripting** functoid con plantillas de llamada XSLT en el **script en línea** búfer.|  
|**Ensamblado de script**|Seleccione el ensamblado que desea asociar con el **Scripting** functoid. Sólo los ensamblados a los que se hace referencia en la ventana Proyecto aparecen en esta lista. Asimismo, tenga en cuenta que debe registrar los ensamblados en la GAC.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** está establecido en **ensamblado externo**.|  
|**Clase de secuencia de comandos**|Seleccione la clase del ensamblado elegido que desea **Scripting** functoid para usar.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** está establecido en **ensamblado externo**.|  
|**Método de script**|Seleccione el método de la clase elegida que desea **Scripting** functoid para usar. **Nota:** Asegúrese de que el número de parámetros de entrada que espera el método coincide con el número de parámetros de entrada especificado en el **configurar Functoid de script** cuadro de diálogo.|  
|**Script en línea**|Escriba o copie la secuencia de comandos en línea que se va a utilizar en este cuadro de texto. Idiomas válidos y secuencias de comandos incluyen: plantillas de llamada de C#, JScript. NET, Visual Basic. NET, XSLT y XSLT.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** se establece en uno de los **Inline** configuración. **Precaución:** evite usar más de una vez la misma firma de método. Cuando varios functoids de secuencia de comandos tienen la misma firma de método, BizTalk selecciona la primera implementación y descarta las otras.|  
  
 La siguiente ilustración muestra cómo el **Scripting** functoid aparece en un mapa mediante el script de C# .net a dar formato a un número de teléfono.  
  
 ![Asignar con el C&#35; para dar formato a un número de teléfono. ](../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
Asignación de functoid de secuencia de comandos  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Scripting mediante ensamblados externos](../core/scripting-using-external-assemblies.md)  
  
-   [Scripting mediante C#, JScript .NET y Visual Basic .NET en línea](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [Scripting mediante XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)
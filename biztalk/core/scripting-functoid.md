---
title: Secuencias de comandos de Functoid | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 822bdbc4482a7e16a7458c7c44d128967203f283
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-functoid"></a>Secuencias de comandos (functoid)
El **secuencias de comandos** functoid le permite utilizar secuencias de comandos personalizadas o código en tiempo de ejecución para realizar funciones de lo contrario no está disponibles. Por ejemplo, puede llamar a un ensamblado de .NET en tiempo de ejecución mediante la **secuencias de comandos** functoid y escribir sus propias funciones personalizadas.  
  
 El **secuencias de comandos** functoid es compatible con los siguientes idiomas:  
  
-   C# .NET  
  
-   JScript .NET  
  
-   Visual Basic .NET  
  
-   Transformación de lenguaje de hojas de estilo extensible (XSLT)  
  
-   Plantillas de llamada de XSLT  
  
 Otra diferencia importante entre actual **secuencias de comandos** functoid y en versiones anteriores es que la secuencia de comandos ya no necesita ser creada y almacenada en el functoid. En su lugar, puede crear la secuencia de comandos en un ensamblado .NET independiente y hacer referencia al ensamblado a través de la **Script** propiedad. Al tener la secuencia de comandos en un ensamblado distinto se puede utilizar la misma secuencia de comandos en más de una asignación. Además, es posible que pueda comprar **secuencias de comandos** functoid ensamblados de otros fabricantes.  
  
 Puede usar **secuencias de comandos** functoids creados en versiones anteriores del asignador de BizTalk con la versión actual del asignador de BizTalk. Sin embargo, es necesario que migre primero los functoids. Para obtener más información sobre cómo migrar **secuencias de comandos** functoids, consulte [migrar Functoids](../core/migrating-functoids.md).  
  
 Cuando se agrega un **secuencias de comandos** functoid a un mapa, debe configurar la secuencia de comandos que utiliza el functoid. Si selecciona un **secuencias de comandos** functoid, la **Script** propiedad está habilitada en el **propiedades** ventana. Si hace clic en el botón de puntos suspensivos (**...** ) botón para esta propiedad, el **configurar Functoid de script** abre el cuadro de diálogo. Como alternativa, puede hacer doble clic el **secuencias de comandos** functoid.  
  
 La siguiente tabla muestra los campos de este cuadro de diálogo.  
  
|Campo de cuadro de diálogo Configurar functoid de script|Description|  
|---------------------------------------------------|-----------------|  
|**Seleccionar tipo de script**|Utilice este campo para seleccionar el tipo de script que va a utilizar en este **secuencias de comandos** functoid.<br /><br /> Valores:<br /><br /> -   **Ensamblado externo**. Utilice este valor si desea asociar el **secuencias de comandos** functoid con un ensamblado en la caché global de ensamblados (GAC). **Advertencia:** el código en el ensamblado externo debe ser seguro para subprocesos. En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.<br />-   **C# en línea**.  Utilice este valor si desea asociar el **secuencias de comandos** functoid con código C# en el **script en línea** búfer.<br />-   **JScript .NET en línea**. Utilice este valor si desea asociar el **secuencias de comandos** functoid de secuencia de comandos de JScript .NET en el **script en línea** búfer.<br />-   **En línea Visual Basic .NET**. Utilice este valor si desea asociar el **secuencias de comandos** functoid con código de Visual Basic .NET en el **script en línea** búfer.<br />-   **XSLT en línea**. Utilice este valor si desea asociar el **secuencias de comandos** functoid con XSLT en el **script en línea** búfer.<br />-   **Plantilla de llamada XSLT en línea**. Utilice este valor si desea asociar el **secuencias de comandos** functoid con plantillas de llamada XSLT en el **script en línea** búfer.|  
|**Ensamblado de script**|Seleccione el ensamblado que se va a asociar a la **secuencias de comandos** functoid. Sólo los ensamblados a los que se hace referencia en la ventana Proyecto aparecen en esta lista. Asimismo, tenga en cuenta que debe registrar los ensamblados en la GAC.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** está establecido en **ensamblado externo**.|  
|**Clase de secuencia de comandos**|Seleccione la clase del ensamblado elegido que desea que esto **secuencias de comandos** functoid para usar.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** está establecido en **ensamblado externo**.|  
|**Método de script**|Seleccione el método de la clase elegida que desea que esto **secuencias de comandos** functoid para usar. **Nota:** Asegúrese de que el número de parámetros de entrada que espera el método coincide con el número de parámetros de entrada especificado en el **configurar Functoid de script** cuadro de diálogo.|  
|**Script en línea**|Escriba o copie la secuencia de comandos en línea que se va a utilizar en este cuadro de texto. Idiomas válidos y las secuencias de comandos incluyen: plantillas de llamada de C#, JScript. NET, Visual Basic. NET, XSLT y XSLT.<br /><br /> Este campo solo está disponible cuando **Seleccionar tipo de script** se establece en uno de los **en línea** configuración. **Precaución:** evite utilizar la misma firma de método más de una vez. Cuando varios functoids de secuencia de comandos tienen la misma firma de método, BizTalk selecciona la primera implementación y descarta las otras.|  
  
 La siguiente ilustración muestra cómo el **secuencias de comandos** functoid no aparece en un mapa con la secuencia de comandos de C# .net para cambiar el formato de un número de teléfono.  
  
 ![Asignación mediante la C &#35; para dar formato a un número de teléfono. ] (../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
Asignación de functoid de secuencia de comandos  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Secuencias de comandos con ensamblados externos](../core/scripting-using-external-assemblies.md)  
  
-   [Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)
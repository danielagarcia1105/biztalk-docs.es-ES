---
title: Utilizar BaseFunctoid | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb26a54d-20bf-4302-a5cb-b38e4091002b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f2d1381b1babb26324730c301800d6b0909a411
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-basefunctoid"></a>Utilizar BaseFunctoid
Todos los functoids personalizados deben derivar de la clase **BaseFunctoid** . Primero, debe reemplazar el constructor y realizar un conjunto de llamadas que indiquen al Asignador de BizTalk acerca de su functoid personalizado. A continuación, tiene que escribir la lógica de functoid.  
  
## <a name="overriding-the-constructor"></a>Reemplazar el constructor  
 Debe realizar un número de tareas en el método de reemplazo de constructor de clases para caracterizar su functoid. Estas tareas se suman a todo código específico de functoid que requiera su solución. En la siguiente tabla se describen las tareas principales.  
  
|Tarea|Utilice estos métodos o estas propiedades|Comentarios|  
|----------|-------------------------------------|--------------|  
|Asigne al functoid un identificador único|**ID**|Utilice un valor mayor que 6000 que no se haya utilizado. La utilización de valores menores que 6000 se reserva a functoids internos.|  
|Indique si el functoid tiene efectos secundarios|**HasSideEffects**|El Asignador lo utilizó para optimizar el código XSLT que se genera. Esta propiedad es true de forma predeterminada.|  
|Elija el ensamblado de recursos|**SetupResourceAssembly**|Incluya un archivo de recursos con su proyecto. Si se crea con [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el ensamblado de recursos debe ser **ProjectName.ResourceName**.|  
|Habilite el functoid personalizado para que aparezca en la paleta de Asignador de BizTalk|**SetName**<br /><br /> **SetTooltip**<br /><br /> **SetDescription**<br /><br /> **SetBitmap**|Utilice un identificador de recursos que está señalando a una cadena para el nombre, la información sobre herramientas y la descripción; utilice un mapa de bits de 16 x 16 píxeles.|  
|Asigne el functoid a una o más categorías|**Categoría**|Clasifique el functoid usando uno o más valores [Microsoft.BizTalk.BaseFunctoids.FunctoidCategory](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.functoidcategory.aspx) .|  
|Especifique el número de parámetros aceptados|**SetMinParams**<br /><br /> **SetMaxParams**<br /><br /> **HasVariableInputs**|Use el método **SetMinParams** para establecer el número de parámetros necesarios y el método **SetMaxParams** para establecer el número de parámetros opcionales. Utilice las directrices siguientes para establecer estos valores:<br /><br /> -Si no tiene ningún parámetro opcional, establezca Mín = Máx.<br />-Si tiene algún parámetro opcional, establezca máx = (número de parámetros opcionales - número mínimo de parámetros).<br />-Si desea permitir parámetros opcionales ilimitados, no establezca máximo.<br />-Si tiene un número variable de entradas, realice no establezca Mín o máx. y establecer **HasVariableInputs** = `true`.|  
|Declare qué se puede conectar a su functoid|**AddInputConnectionType**|Llame a **AddInputConnectionType** una vez para cada [Microsoft.BizTalk.BaseFunctoids.ConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) que admite el functoid.|  
|Declare a qué se puede conectar su functoid|**OutputConnectionType**|Use valores de [Microsoft.BizTalk.BaseFunctoids.ConnectionType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.connectiontype.aspx) para indicar al Asignador de BizTalk los tipos de objetos que pueden recibir salida de su functoid. Use **OR** para especificar varios tipos de conexión.|  
|Indique a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] qué métodos invocar para su functoid|**SetExternalFunctionName**<br /><br /> **SetExternalFunctionName2**<br /><br /> **SetExternalFunctionName3**|Para functoids acumulativos, use **SetExternalFunctionName** para establecer la función de inicialización, **SetExternalFunctionName2** para establecer la función de acumulación y **SetExternalFunctionName3** para determinar la función que devuelve el valor acumulado. Para functoids no acumulativos, use **SetExternalFunctionName** para definir el método de functoid.|  
|Tenga el código en línea de uso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para invocar su functoid|**AddScriptTypeSupport SetScriptBuffer**|Llame a **AddScriptTypeSupport** con [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) para habilitar el código en línea. Invoque **SetScriptBuffer** para pasar el código para el functoid. Este código se copiará a la asignación.|  
|Declare variables globales para un functoid en línea|**SetScriptGlobalBuffer**|Cualquier declaración realizada será visible para las otras secuencias de comandos incluidas en la asignación.|  
|Indique qué funciones auxiliares requiere su functoid en línea|**RequiredGlobalHelperFunctions**|Use valores de la enumeración **InlineGlobalHelperFunction** para especificar qué funciones auxiliares son necesarias. Use **OR** para especificar varias funciones auxiliares.|  
|Valide parámetros que hayan pasado a su functoid|**IsDate**<br /><br /> **IsNumeric**|Estas funciones proporcionan una respuesta true/false sin producir una excepción.|  
  
## <a name="implementing-functoid-logic"></a>Implementar lógica de functoid  
 Para que el functoid sea útil, debe implementar uno o varios métodos en función de la categoría de functoid. Si el functoid es acumulativo, es necesario que suministre tres métodos: uno para la inicialización, otro para la acumulación y otro para devolver el valor acumulado. Si el functoid no es acumulativo, es necesario que suministre un método que devuelva un valor.  
  
 También tiene que decidir si el código de implementación de functoid se debe copiar a la asignación p se debe conservar en un ensamblado compilado .NET y si se debe utilizar a través de una referencia.  
  
 Considere la posibilidad de utilizar un functoid en línea cuando:  
  
-   Es correcto que otros lean y modifiquen potencialmente su lógica empresarial.  
  
-   Su functoid depende solo de los espacios de nombres de .NET Framework que admite la asignación. Para espacios de nombres disponibles, vea [secuencias de comandos utilizando C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md).  
  
-   No desea implementar y mantener otro ensamblado con su solución de BizTalk.  
  
-   Está escribiendo una serie de functoids que comparten variables.  
  
 Considere la posibilidad de utilizar un functoid al que se hace referencia cuando:  
  
-   No desea copiar su lógica empresarial en la asignación en la que otras personas la podrían ver o modificar.  
  
-   Su functoid depende de las clases de .NET Framework que no admite la asignación.  
  
-   La funcionalidad agregada proporcionada por el .NET Framework justifica la implementación y el mantenimiento de otro ensamblado con su solución de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un personalizado al que hace referencia de Functoid](../core/developing-a-custom-referenced-functoid.md)   
 [Desarrollar un Functoid en línea personalizado](../core/developing-a-custom-inline-functoid.md)   
 [Desarrollar un Functoid acumulado personalizado](../core/developing-a-custom-cumulative-functoid.md)   
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/Microsoft.BizTalk.BaseFunctoids.BaseFunctoid.aspx)
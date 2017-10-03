---
title: "Desarrollar un Functoid en línea personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4533f09f-b62d-4b09-b7de-44541c6cf053
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a742e6a53b5fb81d92922ff94e7754239f723ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-a-custom-inline-functoid"></a>Desarrollar un functoid en línea personalizado
Los functoids en línea personalizados proporcionan funcionalidad al copiar directamente el código de implementación en una asignación, en lugar de hacer referencia a un ensamblado, una clase y un nombre de método como en el caso de los functoids personalizados a los que se hace referencia.  
  
## <a name="building-inline-script"></a>Generar una secuencia de comandos en línea  
 Hay dos formas de proporcionar una secuencia de comandos para incluirla en la asignación. Seleccione uno de los métodos siguientes según si el functoid personalizado es compatible con un número variable de parámetros:  
  
-   Invalidar **GetInlineScriptBuffer** cuando el functoid personalizado acepta un número variable de parámetros de entrada y ha establecido la **HasVariableInputs** propiedad `true`. Por ejemplo, utilice este método si desea concatenar un número variable de cadenas o buscar el valor más grande de un conjunto de valores.  
  
-   Use **SetScriptBuffer** cuando no es necesario admitir un número variable de parámetros de entrada. Aunque puede seguir utilizando parámetros opcionales, el número total de parámetros es fijo.  
  
 Estos dos métodos requieren implementaciones diferentes.  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a>Proporcionar código en línea con SetScriptBuffer  
 Para configurar el functoid personalizado para usar la secuencia de comandos en línea:  
  
1.  Llame a **AddScriptTypeSupport** con [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) para permitir que el código insertado y establezca el tipo de secuencia de comandos compatible.  
  
2.  Invocar **SetScriptBuffer** para establecer el código que se utilizará para el functoid personalizado. Debe llamar esta función tres veces con el parámetro `functionNumber` en el caso de los functoids acumulativos personalizados y una vez en el caso de los functoids no acumulativos personalizados.  
  
3.  Use **SetScriptGlobalBuffer** para declarar las variables globales que utilice el código en línea.  
  
4.  Use **RequiredGlobalHelperFunctions** para indicar las funciones auxiliares que requiere su functoid en línea personalizado.  
  
 Puede generar la secuencia de comandos mediante StringBuilder o constantes. Un enfoque para escribir código de secuencias de comandos es escribir primero un functoid personalizado al que se hace referencia y, cuando se hayan eliminado todos los errores, convertirlo a en línea mediante la copia de las funciones correspondientes a constantes de cadena.  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a>Proporcionar código en línea con GetInlineScriptBuffer  
 Si el functoid en línea personalizado es compatible con un número variable de parámetros, deberá reemplazar **GetInlineScriptBuffer**. Para configurar el functoid personalizado para usar la secuencia de comandos en línea:  
  
1.  En el constructor, declare que el functoid personalizado tiene entradas variables estableciendo **HasVariableInputs** a `true`.  
  
2.  En el constructor, llame a **AddScriptTypeSupport** con [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) para permitir que el código insertado y establezca el tipo de secuencia de comandos compatible.  
  
3.  Invalidar **GetInlineScriptBuffer** para construir y devolver el código que se usará en el mapa para el functoid personalizado. Use los parámetros para generar el código correcto mediante la selección de `scriptType` y `numParams`. El último parámetro, `functionNumber`, debe ser 0. Esto es porque las funciones acumulativas tienen un número fijo de entradas y no utilizan este mecanismo.  
  
4.  Use **SetScriptGlobalBuffer** para declarar variables globales que utilice el código en línea.  
  
5.  Use **RequiredGlobalHelperFunctions** para indicar las funciones auxiliares que requiere su functoid en línea personalizado.  
  
 El siguiente fragmento de código genera una función C# con el número de parámetros pasados en `numParams`, pero sin ningún cuerpo de función. Para usar este fragmento de código, copie el ejemplo a la solución y agregue código para hacer algo con los parámetros y devolver un valor.  
  
```  
// Override GetInlineScriptBuffer  
protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
{  
    // Is this one of the supported script types?  
    if(ScriptType.CSharp == scriptType)  
    {  
        // Assume functionNumber == 0  
        StringBuilder builder = new StringBuilder();  
        // Function declaration   
        builder.Append("public string MyFunction("  
        // Declare parameters using numParams  
        for(int i=0; i<numParams; i++)  
        {  
            // Separate params with a comma  
            if(i > 0)  
                builder.Append(", ");  
            // Declare parameters, param0 to paramNUMPARAM  
            builder.Append("string param" + i.ToString());  
        }  
        builder.Append(")\n");  
        // Function body; process params as needed  
        builder.Append("{\n");  
        builder.Append("}\n");  
        // Return script  
        return builder.ToString();  
    }  
    // scriptType is unsupported  
    return string.Empty;  
}  
```  
  
## <a name="testing-an-inline-script"></a>Comprobar una secuencia de comandos en línea  
 La realización de pruebas merece una consideración especial en cualquier esfuerzo de desarrollo. Las pruebas de los functoids en línea personalizados pueden ser complejas. Para simplificar el proceso, utilice una o las dos técnicas siguientes:  
  
-   Examinar el XSLT de una asignación que use el functoid en línea personalizado.  
  
-   Comprobar la entrada y la salida de una asignación que use el functoid en línea personalizado  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a>Examinar el XSLT de una asignación que use el functoid en línea personalizado  
 Esta técnica suele revelar problemas de lógica o de sintaxis sutiles. También ayuda a comprender lo que ocurre en la asignación.  
  
 Para ver el XSLT de una asignación:  
  
1.  En un proyecto de BizTalk de Visual Studio, haga clic en el **el Explorador de soluciones** pestaña, haga clic en un mapa que use el functoid en línea personalizado y, a continuación, haga clic en **validar asignación**.  
  
2.  Desplácese a la ventana Resultados para buscar la dirección URL del archivo XSLT. Presione CTRL y haga clic en la dirección URL para ver el archivo.  
  
> [!NOTE]
>  Recuerde que cualquier cambio realizado en el archivo XSLT no se reflejará en el functoid personalizado.  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a>Comprobar una asignación que use el functoid en línea personalizado  
 Esta técnica comprueba si la asignación y el functoid en línea personalizado funcionan del modo previsto.  
  
 Para comprobar una asignación:  
  
1.  En un proyecto de BizTalk de Visual Studio, haga clic en el **el Explorador de soluciones** pestaña, haga clic en un mapa que use el functoid en línea personalizado y, a continuación, haga clic en **comprobar asignación**.  
  
2.  Desplácese a la ventana Resultados para buscar la dirección URL del archivo de salida. Presione CTRL y haga clic en la dirección URL para ver el archivo.  
  
 Puede comprobar los valores de entrada y de salida para comprobar si el comportamiento de la asignación ha sido el previsto.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo ilustra cómo crear un functoid en línea personalizado para la concatenación de dos cadenas. Se basa en un archivo de recursos que contiene tres recursos de cadena y un recurso de mapa de bits de 16 x 16 píxeles.  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
using System.Text;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation using inline code.  
    /// </summary>  
    public class CustomStringConcatFunctoid : BaseFunctoid  
    {  
        public CustomStringConcatFunctoid()  
            : base()  
        {  
            //ID for this functoid  
            this.ID = 6001;  
  
            // Resource assembly must be ProjectName.ResourceName if building with VS.Net  
            SetupResourceAssembly("Microsoft.Samples.BizTalk.CustomFunctoid.CustomFunctoidResources", Assembly.GetExecutingAssembly());  
  
            // Pass the resource ID names for functoid name, tooltip  
            // description and the 16x16 bitmap for the Map palette  
            SetName("IDS_CUSTOMSTRINGCONCATFUNCTOID_NAME");  
            SetTooltip("IDS_CUSTOMSTRINGCONCATFUNCTOID_TOOLTIP");  
            SetDescription("IDS_CUSTOMSTRINGCONCATFUNCTOID_DESCRIPTION");  
            SetBitmap("IDB_CUSTOMSTRINGCONCATFUNCTOID_BITMAP");  
  
            // Put this string handling function under the String   
            // Functoid tab in the Visual Studio toolbox for functoids  
            this.Category = FunctoidCategory.String;  
  
            // 2 required parameters, no optional parameters  
            this.SetMinParams(2);  
            this.SetMaxParams(2);  
  
            // Functoid accepts two inputs  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
            AddInputConnectionType(ConnectionType.AllExceptRecord);  
  
            // Set the output connection type  
            this.OutputConnectionType = ConnectionType.AllExceptRecord;  
  
            // Declare support for CSharp inline function and  
            // pass the method implementation to the buffer  
            AddScriptTypeSupport(ScriptType.CSharp);  
            SetScriptBuffer(ScriptType.CSharp, GetCSharpBuffer());  
        }  
  
        private string GetCSharpBuffer()  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string ConCatStrings(string val1, string val2)\n");  
            builder.Append("{\n");  
            builder.Append("    return val2+val1;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilizar BaseFunctoid](../core/using-basefunctoid.md)   
 [Desarrollar un personalizado al que hace referencia de Functoid](../core/developing-a-custom-referenced-functoid.md)   
 [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md)
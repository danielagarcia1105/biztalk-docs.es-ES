---
title: Desarrollar un Functoid en línea personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4533f09f-b62d-4b09-b7de-44541c6cf053
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a742e6a53b5fb81d92922ff94e7754239f723ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242020"
---
# <a name="developing-a-custom-inline-functoid"></a><span data-ttu-id="842e9-102">Desarrollar un functoid en línea personalizado</span><span class="sxs-lookup"><span data-stu-id="842e9-102">Developing a Custom Inline Functoid</span></span>
<span data-ttu-id="842e9-103">Los functoids en línea personalizados proporcionan funcionalidad al copiar directamente el código de implementación en una asignación, en lugar de hacer referencia a un ensamblado, una clase y un nombre de método como en el caso de los functoids personalizados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="842e9-103">Custom inline functoids provide functionality by copying implementation code directly into a map and not by referencing an assembly, class, and method name like a custom referenced functoid.</span></span>  
  
## <a name="building-inline-script"></a><span data-ttu-id="842e9-104">Generar una secuencia de comandos en línea</span><span class="sxs-lookup"><span data-stu-id="842e9-104">Building Inline Script</span></span>  
 <span data-ttu-id="842e9-105">Hay dos formas de proporcionar una secuencia de comandos para incluirla en la asignación.</span><span class="sxs-lookup"><span data-stu-id="842e9-105">There are two ways to provide script for inclusion into the map.</span></span> <span data-ttu-id="842e9-106">Seleccione uno de los métodos siguientes según si el functoid personalizado es compatible con un número variable de parámetros:</span><span class="sxs-lookup"><span data-stu-id="842e9-106">Choose from the following methods, based on whether your custom functoid supports a variable number of parameters:</span></span>  
  
-   <span data-ttu-id="842e9-107">Invalidar **GetInlineScriptBuffer** cuando el functoid personalizado acepta un número variable de parámetros de entrada y ha establecido la **HasVariableInputs** propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="842e9-107">Override **GetInlineScriptBuffer** when your custom functoid accepts a variable number of input parameters and you have set the **HasVariableInputs** property to `true`.</span></span> <span data-ttu-id="842e9-108">Por ejemplo, utilice este método si desea concatenar un número variable de cadenas o buscar el valor más grande de un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="842e9-108">For example, use this method if you want to concatenate a variable number of strings or find the largest value in a set of values.</span></span>  
  
-   <span data-ttu-id="842e9-109">Use **SetScriptBuffer** cuando no es necesario admitir un número variable de parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="842e9-109">Use **SetScriptBuffer** when you do not need to support a variable number of input parameters.</span></span> <span data-ttu-id="842e9-110">Aunque puede seguir utilizando parámetros opcionales, el número total de parámetros es fijo.</span><span class="sxs-lookup"><span data-stu-id="842e9-110">You can still use optional parameters, but the total number of parameters is fixed.</span></span>  
  
 <span data-ttu-id="842e9-111">Estos dos métodos requieren implementaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="842e9-111">These two methods require different implementations.</span></span>  
  
### <a name="providing-inline-code-with-setscriptbuffer"></a><span data-ttu-id="842e9-112">Proporcionar código en línea con SetScriptBuffer</span><span class="sxs-lookup"><span data-stu-id="842e9-112">Providing Inline Code with SetScriptBuffer</span></span>  
 <span data-ttu-id="842e9-113">Para configurar el functoid personalizado para usar la secuencia de comandos en línea:</span><span class="sxs-lookup"><span data-stu-id="842e9-113">To configure your custom functoid to use inline script:</span></span>  
  
1.  <span data-ttu-id="842e9-114">Llame a **AddScriptTypeSupport** con [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) para permitir que el código insertado y establezca el tipo de secuencia de comandos compatible.</span><span class="sxs-lookup"><span data-stu-id="842e9-114">Call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
2.  <span data-ttu-id="842e9-115">Invocar **SetScriptBuffer** para establecer el código que se utilizará para el functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-115">Invoke **SetScriptBuffer** to set the code to use for the custom functoid.</span></span> <span data-ttu-id="842e9-116">Debe llamar esta función tres veces con el parámetro `functionNumber` en el caso de los functoids acumulativos personalizados y una vez en el caso de los functoids no acumulativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="842e9-116">You will call this function three times with the `functionNumber` parameter for custom cumulative functoids and once for custom noncumulative functoids.</span></span>  
  
3.  <span data-ttu-id="842e9-117">Use **SetScriptGlobalBuffer** para declarar las variables globales que utilice el código en línea.</span><span class="sxs-lookup"><span data-stu-id="842e9-117">Use **SetScriptGlobalBuffer** to declare any global variables that your inline code uses.</span></span>  
  
4.  <span data-ttu-id="842e9-118">Use **RequiredGlobalHelperFunctions** para indicar las funciones auxiliares que requiere su functoid en línea personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-118">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
 <span data-ttu-id="842e9-119">Puede generar la secuencia de comandos mediante StringBuilder o constantes.</span><span class="sxs-lookup"><span data-stu-id="842e9-119">You can build your script by using StringBuilder or constants.</span></span> <span data-ttu-id="842e9-120">Un enfoque para escribir código de secuencias de comandos es escribir primero un functoid personalizado al que se hace referencia y, cuando se hayan eliminado todos los errores, convertirlo a en línea mediante la copia de las funciones correspondientes a constantes de cadena.</span><span class="sxs-lookup"><span data-stu-id="842e9-120">One approach to writing script code is to write a custom referenced functoid first and, when all bugs are eliminated, convert it to inline by copying your functions into string constants.</span></span>  
  
### <a name="providing-inline-code-with-getinlinescriptbuffer"></a><span data-ttu-id="842e9-121">Proporcionar código en línea con GetInlineScriptBuffer</span><span class="sxs-lookup"><span data-stu-id="842e9-121">Providing Inline Code with GetInlineScriptBuffer</span></span>  
 <span data-ttu-id="842e9-122">Si el functoid en línea personalizado es compatible con un número variable de parámetros, deberá reemplazar **GetInlineScriptBuffer**.</span><span class="sxs-lookup"><span data-stu-id="842e9-122">If your custom inline functoid supports a variable number of parameters, you will override **GetInlineScriptBuffer**.</span></span> <span data-ttu-id="842e9-123">Para configurar el functoid personalizado para usar la secuencia de comandos en línea:</span><span class="sxs-lookup"><span data-stu-id="842e9-123">To configure your custom functoid to use inline script:</span></span>  
  
1.  <span data-ttu-id="842e9-124">En el constructor, declare que el functoid personalizado tiene entradas variables estableciendo **HasVariableInputs** a `true`.</span><span class="sxs-lookup"><span data-stu-id="842e9-124">In the constructor, declare that your custom functoid has variable inputs by setting **HasVariableInputs** to `true`.</span></span>  
  
2.  <span data-ttu-id="842e9-125">En el constructor, llame a **AddScriptTypeSupport** con [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) para permitir que el código insertado y establezca el tipo de secuencia de comandos compatible.</span><span class="sxs-lookup"><span data-stu-id="842e9-125">In the constructor, call **AddScriptTypeSupport** with [Microsoft.BizTalk.BaseFunctoids.ScriptType](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.scripttype.aspx) to enable inline code and set the supported script type.</span></span>  
  
3.  <span data-ttu-id="842e9-126">Invalidar **GetInlineScriptBuffer** para construir y devolver el código que se usará en el mapa para el functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-126">Override **GetInlineScriptBuffer** to construct and return the code to use in the map for your custom functoid.</span></span> <span data-ttu-id="842e9-127">Use los parámetros para generar el código correcto mediante la selección de `scriptType` y `numParams`.</span><span class="sxs-lookup"><span data-stu-id="842e9-127">Use the parameters to build the correct code by checking the `scriptType` and `numParams`.</span></span> <span data-ttu-id="842e9-128">El último parámetro, `functionNumber`, debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="842e9-128">The final parameter, `functionNumber`, should be 0.</span></span> <span data-ttu-id="842e9-129">Esto es porque las funciones acumulativas tienen un número fijo de entradas y no utilizan este mecanismo.</span><span class="sxs-lookup"><span data-stu-id="842e9-129">This is because cumulative functions have a fixed number of inputs and do not use this mechanism.</span></span>  
  
4.  <span data-ttu-id="842e9-130">Use **SetScriptGlobalBuffer** para declarar variables globales que utilice el código en línea.</span><span class="sxs-lookup"><span data-stu-id="842e9-130">Use **SetScriptGlobalBuffer** to declare global variables that your inline code uses.</span></span>  
  
5.  <span data-ttu-id="842e9-131">Use **RequiredGlobalHelperFunctions** para indicar las funciones auxiliares que requiere su functoid en línea personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-131">Use **RequiredGlobalHelperFunctions** to indicate the helper functions that your custom inline functoid requires.</span></span>  
  
 <span data-ttu-id="842e9-132">El siguiente fragmento de código genera una función C# con el número de parámetros pasados en `numParams`, pero sin ningún cuerpo de función.</span><span class="sxs-lookup"><span data-stu-id="842e9-132">The following code fragment builds a C# function with the number of parameters passed in `numParams` but with no function body.</span></span> <span data-ttu-id="842e9-133">Para usar este fragmento de código, copie el ejemplo a la solución y agregue código para hacer algo con los parámetros y devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="842e9-133">To use this code fragment, copy the example to your solution and add code to do something with the parameters and return a value.</span></span>  
  
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
  
## <a name="testing-an-inline-script"></a><span data-ttu-id="842e9-134">Comprobar una secuencia de comandos en línea</span><span class="sxs-lookup"><span data-stu-id="842e9-134">Testing an Inline Script</span></span>  
 <span data-ttu-id="842e9-135">La realización de pruebas merece una consideración especial en cualquier esfuerzo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="842e9-135">Testing is an important consideration in any development effort.</span></span> <span data-ttu-id="842e9-136">Las pruebas de los functoids en línea personalizados pueden ser complejas.</span><span class="sxs-lookup"><span data-stu-id="842e9-136">Custom inline functoids can be challenging to test.</span></span> <span data-ttu-id="842e9-137">Para simplificar el proceso, utilice una o las dos técnicas siguientes:</span><span class="sxs-lookup"><span data-stu-id="842e9-137">To simplify the process, use one or both of the following techniques:</span></span>  
  
-   <span data-ttu-id="842e9-138">Examinar el XSLT de una asignación que use el functoid en línea personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-138">Examine the XSLT of a map that uses the custom inline functoid.</span></span>  
  
-   <span data-ttu-id="842e9-139">Comprobar la entrada y la salida de una asignación que use el functoid en línea personalizado</span><span class="sxs-lookup"><span data-stu-id="842e9-139">Verify the input and output of a map that uses the custom inline functoid.</span></span>  
  
### <a name="examine-the-xslt-of-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="842e9-140">Examinar el XSLT de una asignación que use el functoid en línea personalizado</span><span class="sxs-lookup"><span data-stu-id="842e9-140">Examine the XSLT of a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="842e9-141">Esta técnica suele revelar problemas de lógica o de sintaxis sutiles.</span><span class="sxs-lookup"><span data-stu-id="842e9-141">This technique often reveals problems with logic or subtle syntax issues.</span></span> <span data-ttu-id="842e9-142">También ayuda a comprender lo que ocurre en la asignación.</span><span class="sxs-lookup"><span data-stu-id="842e9-142">It also helps you to understand what happens in the map.</span></span>  
  
 <span data-ttu-id="842e9-143">Para ver el XSLT de una asignación:</span><span class="sxs-lookup"><span data-stu-id="842e9-143">To view the XSLT for a map:</span></span>  
  
1.  <span data-ttu-id="842e9-144">En un proyecto de BizTalk de Visual Studio, haga clic en el **el Explorador de soluciones** pestaña, haga clic en un mapa que use el functoid en línea personalizado y, a continuación, haga clic en **validar asignación**.</span><span class="sxs-lookup"><span data-stu-id="842e9-144">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="842e9-145">Desplácese a la ventana Resultados para buscar la dirección URL del archivo XSLT.</span><span class="sxs-lookup"><span data-stu-id="842e9-145">Scroll the Output window to find the URL for the XSLT file.</span></span> <span data-ttu-id="842e9-146">Presione CTRL y haga clic en la dirección URL para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="842e9-146">Press CTRL and click the URL to view the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="842e9-147">Recuerde que cualquier cambio realizado en el archivo XSLT no se reflejará en el functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="842e9-147">Remember that any changes made to the XSLT file will not be reflected in your custom functoid.</span></span>  
  
### <a name="test-a-map-that-uses-the-custom-inline-functoid"></a><span data-ttu-id="842e9-148">Comprobar una asignación que use el functoid en línea personalizado</span><span class="sxs-lookup"><span data-stu-id="842e9-148">Test a Map That Uses the Custom Inline Functoid</span></span>  
 <span data-ttu-id="842e9-149">Esta técnica comprueba si la asignación y el functoid en línea personalizado funcionan del modo previsto.</span><span class="sxs-lookup"><span data-stu-id="842e9-149">This tests whether the map and custom inline functoid work as expected.</span></span>  
  
 <span data-ttu-id="842e9-150">Para comprobar una asignación:</span><span class="sxs-lookup"><span data-stu-id="842e9-150">To test a map:</span></span>  
  
1.  <span data-ttu-id="842e9-151">En un proyecto de BizTalk de Visual Studio, haga clic en el **el Explorador de soluciones** pestaña, haga clic en un mapa que use el functoid en línea personalizado y, a continuación, haga clic en **comprobar asignación**.</span><span class="sxs-lookup"><span data-stu-id="842e9-151">From a Visual Studio BizTalk project, click the **Solution Explorer** tab, right-click a map that uses your custom inline functoid, and then click **Test Map**.</span></span>  
  
2.  <span data-ttu-id="842e9-152">Desplácese a la ventana Resultados para buscar la dirección URL del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="842e9-152">Scroll the Output window to find the URL for the output file.</span></span> <span data-ttu-id="842e9-153">Presione CTRL y haga clic en la dirección URL para ver el archivo.</span><span class="sxs-lookup"><span data-stu-id="842e9-153">Press CTRL and click the URL to view the file.</span></span>  
  
 <span data-ttu-id="842e9-154">Puede comprobar los valores de entrada y de salida para comprobar si el comportamiento de la asignación ha sido el previsto.</span><span class="sxs-lookup"><span data-stu-id="842e9-154">You can check input and output values to verify that the map behaved as expected.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842e9-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="842e9-155">Example</span></span>  
 <span data-ttu-id="842e9-156">El siguiente ejemplo ilustra cómo crear un functoid en línea personalizado para la concatenación de dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="842e9-156">The following example illustrates how to create a custom inline functoid for concatenating two strings.</span></span> <span data-ttu-id="842e9-157">Se basa en un archivo de recursos que contiene tres recursos de cadena y un recurso de mapa de bits de 16 x 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="842e9-157">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="842e9-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="842e9-158">See Also</span></span>  
 <span data-ttu-id="842e9-159">[Utilizar BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="842e9-159">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="842e9-160">[Desarrollar un personalizado al que hace referencia de Functoid](../core/developing-a-custom-referenced-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="842e9-160">[Developing a Custom Referenced Functoid](../core/developing-a-custom-referenced-functoid.md) </span></span>  
 [<span data-ttu-id="842e9-161">Functoid personalizado (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="842e9-161">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)
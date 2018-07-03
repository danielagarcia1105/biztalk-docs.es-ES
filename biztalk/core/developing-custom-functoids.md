---
title: Desarrollar Functoids personalizados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77419e1f-9f01-44ac-bf5b-a393f1d17f61
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc424533a859f33a139c081897164e9f5db25b2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019899"
---
# <a name="developing-custom-functoids"></a><span data-ttu-id="7d9fc-102">Desarrollar Functoids personalizados</span><span class="sxs-lookup"><span data-stu-id="7d9fc-102">Developing Custom Functoids</span></span>
<span data-ttu-id="7d9fc-103">Aunque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona muchos functoids para admitir una gran cantidad de operaciones diferentes, probablemente se encontrará con una situación que requiera un enfoque distinto.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-103">Although [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides many functoids to support a range of diverse operations, you will likely encounter a situation that requires a different approach.</span></span> <span data-ttu-id="7d9fc-104">Los functoids personalizados proporcionan una forma de ampliar la variedad de operaciones disponibles dentro del entorno de asignación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d9fc-104">Custom functoids provide a way for you to extend the range of operations available within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mapping environment.</span></span> <span data-ttu-id="7d9fc-105">Cada functoid personalizado se implementa como un ensamblado .NET utilizando las clases derivados de **Microsoft.BizTalk.BaseFunctoids**.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-105">Each custom functoid is deployed as a .NET assembly using classes derived from **Microsoft.BizTalk.BaseFunctoids**.</span></span> <span data-ttu-id="7d9fc-106">Un ensamblado puede contener más de un functoid personalizado.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-106">An assembly can contain more than one custom functoid.</span></span>  
  
 <span data-ttu-id="7d9fc-107">Debería considerar la posibilidad de utilizar un functoid personalizado en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d9fc-107">You should consider using a custom functoid in the following scenarios:</span></span>  
  
- <span data-ttu-id="7d9fc-108">Existen reglas de conversión y validación especiales para un campo de código de carácter que utiliza datos a los que solo se puede obtener acceso a través de un API antiguo del propietario.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-108">You have special validation and conversion rules for a character code field using data that is only accessible through a proprietary legacy API.</span></span>  
  
- <span data-ttu-id="7d9fc-109">Debe cifrar o descifrar campos mediante lógica empresarial personalizada y administración de claves.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-109">You need to encrypt or decrypt fields using custom business logic and key management.</span></span>  
  
- <span data-ttu-id="7d9fc-110">Necesita generar un código hash desde una parte del mensaje para utilizarlo en otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-110">You need to generate a hash code from part of the message for use in another application.</span></span>  
  
- <span data-ttu-id="7d9fc-111">Las solicitudes de administración de cuentas que transmitieron los mensajes a sus departamentos incluyen información de resumen acerca de ventas totales por cada tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-111">Accounting requests that messages transmitted to their department include summary information about total sales by each product type.</span></span>  
  
- <span data-ttu-id="7d9fc-112">Si desea reducir la complejidad de una asignación, combine varios pasos relacionados, utilice un enfoque distinto o utilice bibliotecas de clases nuevas.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-112">You want to reduce the complexity of a map by combining several related steps, by using a different approach, or by using new class libraries.</span></span>  
  
- <span data-ttu-id="7d9fc-113">Más de una asignación utiliza el mismo código de secuencia de comandos en un functoid de secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-113">More than one map is using the same script code in a script functoid.</span></span>  
  
- <span data-ttu-id="7d9fc-114">Cuando se produce un error en una operación, lo debe escribir en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-114">You need to write to the event log when an operation fails.</span></span>  
  
  <span data-ttu-id="7d9fc-115">Los functoids personalizados se puede integrar en una solución directamente mediante un código en línea o, indirectamente, al hacer referencia a un método en una biblioteca de clases implementada en la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-115">Custom functoids can be integrated into a solution directly by using inline code or indirectly by reference to a method in a class library deployed into the global assembly cache.</span></span> <span data-ttu-id="7d9fc-116">Ambos tipos de integración se basan en el **BizTalk.BaseFunctoid** clase y siga el mismo conjunto de pasos generales:</span><span class="sxs-lookup"><span data-stu-id="7d9fc-116">Both types of integration rely on the **BizTalk.BaseFunctoid** class and follow the same set of general steps:</span></span>  
  
1. <span data-ttu-id="7d9fc-117">Cree un proyecto de biblioteca de clases nueva mediante el lenguaje .NET que prefiera.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-117">Create a new class library project using the .NET language of your choice.</span></span>  
  
2. <span data-ttu-id="7d9fc-118">Mediante la utilidad de nombre seguro sn.exe, cree un keyfile y asígnelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-118">Using the strong-naming utility sn.exe, create a keyfile and assign it to the project.</span></span>  
  
3. <span data-ttu-id="7d9fc-119">Agregue una referencia a Microsoft.BizTalk.BaseFunctoids.dll.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-119">Add a reference to Microsoft.BizTalk.BaseFunctoids.dll.</span></span> <span data-ttu-id="7d9fc-120">Este ensamblado contiene el **BaseFunctoid** clase base.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-120">This assembly contains the **BaseFunctoid** base class.</span></span>  
  
4. <span data-ttu-id="7d9fc-121">Cree un archivo de recursos y agréguelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-121">Create a resource file and add it to the project.</span></span> <span data-ttu-id="7d9fc-122">Agregue recursos de cadena para el nombre de functoid, la información sobre herramientas y la descripción.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-122">Add string resources for the functoid name, tooltip, and description.</span></span> <span data-ttu-id="7d9fc-123">Agregue un recurso de imagen de 16 x 16 píxeles para representar el functoid en la paleta de diseñador de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-123">Add a 16x16-pixel image resource to represent the functoid on the map designer palette.</span></span>  
  
5. <span data-ttu-id="7d9fc-124">Implementar la clase de functoid derivando de **BaseFunctoid**, establecer los parámetros básicos en el constructor y, a continuación, escribir el método de functoid y cualquier método compatible.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-124">Implement the functoid class by deriving from **BaseFunctoid**, establishing basic parameters in the constructor, and then writing the functoid method and any supporting methods.</span></span> <span data-ttu-id="7d9fc-125">El ensamblado puede contener varios functoids personalizados.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-125">The assembly can contain multiple custom functoids.</span></span>  
  
6. <span data-ttu-id="7d9fc-126">Implemente el ensamblado y asegúrese de que el functoid nuevo está disponible de la paleta de Cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-126">Deploy the assembly and ensure the new functoid is available from the Toolbox palette.</span></span> <span data-ttu-id="7d9fc-127">Consulte [agregar y quitar Functoids personalizados del cuadro de herramientas de Visual Studio](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="7d9fc-127">See [Adding and Removing Custom Functoids from the Visual Studio Toolbox](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md).</span></span>  
  
   <span data-ttu-id="7d9fc-128">A continuación se proporciona es una ilustración del functoid Floor.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-128">The following is an illustration for Floor functoid.</span></span>  
  
```  
/// <summary>  
/// Floor Functoid - finds the floor of input  
/// </summary>  
public class FloorFunctoid : BaseFunctoid  
{  
    public FloorFunctoid()  
        : base()  
    {  
        this.ID = 11001;  
        SetupResourceAssembly("MultipleFunctoids.Resource", Assembly.GetExecutingAssembly());  
  
        SetName("NAME_FLOOR");  
        SetDescription("DESCRIPTION_FLOOR");  
        SetTooltip("DESCRIPTION_FLOOR");  
        SetBitmap("IMAGE_FLOOR");  
  
        SetExternalFunctionName(GetType().Assembly.FullName, " MultipleFunctoids.FloorFunctoid", "MathFloor");  
        this.RequiredGlobalHelperFunctions = InlineGlobalHelperFunction.IsNumeric;  
  
        AddScriptTypeSupport(ScriptType.CSharp);  
        SetMinParams(1);  
        SetMaxParams(1);  
  
        this.Category = FunctoidCategory.Math;  
        this.OutputConnectionType = ConnectionType.AllExceptRecord;  
        AddInputConnectionType(ConnectionType.AllExceptRecord);  
        this.HasSideEffects = false;  
    }  
  
    /// <summary>  
    /// To create the C# function  
    /// </summary>  
    /// <param name="scriptType">Script type</param>  
    /// <param name="numParams">Number of parameters</param>  
    /// <param name="functionNumber">Functoid number</param>  
    /// <returns>C# script</returns>  
    protected override string GetInlineScriptBuffer(ScriptType scriptType, int numParams, int functionNumber)  
    {  
        if (ScriptType.CSharp == scriptType)  
        {  
            StringBuilder builder = new StringBuilder();  
  
            builder.Append("public string MathFloor(string input)\n");  
            builder.Append("{\n");  
            builder.Append("  if(string.IsNullOrEmpty(input))\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("double d = 0.0;\n");  
            builder.Append("if (IsNumeric(input, ref d))\n");  
            builder.Append("    return Math.Floor(d).ToString(System.Globalization.CultureInfo.InvariantCulture);\n");  
            builder.Append("else\n");  
            builder.Append("    return string.Empty;\n");  
            builder.Append("}\n");  
  
            return builder.ToString();  
        }  
        else  
        {  
            return string.Empty;  
        }  
    }  
}  
  
```  
  
 <span data-ttu-id="7d9fc-129">Al usar este código de ejemplo como parte del proyecto de C#, el "Nombre de ensamblado" debe establecerse en "MultipleFunctoids".</span><span class="sxs-lookup"><span data-stu-id="7d9fc-129">While using this sample code as part of your C# project, the “Assembly name” must be set to “MultipleFunctoids”.</span></span> <span data-ttu-id="7d9fc-130">El proyecto de C# (que contiene este código) debe incluir un archivo Resource.resx.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-130">Your C# project (containing this code) should include a Resource.resx file.</span></span>  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 <span data-ttu-id="7d9fc-131">En el código anterior, los valores "NAME_FLOOR", "DESCRIPTION_FLOOR" y "DESCRIPTION_FLOOR" son las "claves" de las cadenas de recursos incrustadas en el archivo Resource.resx.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-131">In the above code, the values “NAME_FLOOR”, “DESCRIPTION_FLOOR”, and “DESCRIPTION_FLOOR” are the “keys” of resource strings embedded in Resource.resx file.</span></span> <span data-ttu-id="7d9fc-132">Además, "IMAGE_FLOOR" es el nombre de una imagen incrustada en el archivo Resource.resx.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-132">And, “IMAGE_FLOOR” is the name of an image embedded in the Resource.resx file.</span></span> <span data-ttu-id="7d9fc-133">Esta imagen actuará como icono para el functoid.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-133">This image will act as an icon for the functoid.</span></span>  
  
 <span data-ttu-id="7d9fc-134">Si no especifica claves de recursos adecuadas, o si elimina el método SetName, se creará un functoid personalizado sin nombre, lo cual no es un método recomendado.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-134">If you do not specify proper resource keys, or if you delete the SetName method, then a nameless custom functoid is created, which is not a good practice.</span></span> <span data-ttu-id="7d9fc-135">Lo mismo puede decirse de los métodos SetDescription y SetTooltip.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-135">Same holds true for SetDescription and SetTooltip methods.</span></span> <span data-ttu-id="7d9fc-136">Use siempre correctamente estos métodos para evitar un comportamiento de eliminación no deseado.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-136">Always use these methods properly to avoid any unwanted garbage behavior.</span></span> <span data-ttu-id="7d9fc-137">No obstante, puede omitir el método SetBitmap si no tiene ninguna imagen adecuada para usar como iconos de functoid.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-137">However, you may skip the SetBitmap method if you do not have any suitable images to be used as functoid icons.</span></span> <span data-ttu-id="7d9fc-138">En tal caso, el functoid personalizado usa un icono predeterminado, que es inocuo (a menos que haya varios functoids sin iconos).</span><span class="sxs-lookup"><span data-stu-id="7d9fc-138">In such a case, a default icon is used by the custom functoid, which is harmless (unless there are multiple icon-less functoids).</span></span>  
  
 <span data-ttu-id="7d9fc-139">Para obtener más información sobre cómo crear un functoid personalizado, consulte [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7d9fc-139">For more information about how to create a custom functoid, see [Custom Functoid (BizTalk Server Sample)](../core/custom-functoid-biztalk-server-sample.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7d9fc-140">Ciertos identificadores de functoid están reservados para functoids del Asignador estándar o integrados.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-140">Certain functoid IDs are reserved by standard/inbuilt Mapper functoids.</span></span> <span data-ttu-id="7d9fc-141">Normalmente, los functoids del asignador estándares usan los identificadores del 1 a 10000.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-141">Usually, the standard Mapper functoids use the IDs from 1 to 10000.</span></span> <span data-ttu-id="7d9fc-142">Al crear functoids personalizados, no use identificadores de functoid inferiores a 10.000.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-142">While creating custom functoids, do not use the functoid IDs less than 10000.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d9fc-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7d9fc-143">In This Section</span></span>  
 <span data-ttu-id="7d9fc-144">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="7d9fc-144">This section contains:</span></span>  
  
-   [<span data-ttu-id="7d9fc-145">Uso de BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="7d9fc-145">Using BaseFunctoid</span></span>](../core/using-basefunctoid.md)  
  
-   [<span data-ttu-id="7d9fc-146">Desarrollo de un functoid personalizado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="7d9fc-146">Developing a Custom Referenced Functoid</span></span>](../core/developing-a-custom-referenced-functoid.md)  
  
-   [<span data-ttu-id="7d9fc-147">Desarrollo de un functoid en línea personalizado</span><span class="sxs-lookup"><span data-stu-id="7d9fc-147">Developing a Custom Inline Functoid</span></span>](../core/developing-a-custom-inline-functoid.md)  
  
-   [<span data-ttu-id="7d9fc-148">Desarrollo de un functoid acumulativo personalizado</span><span class="sxs-lookup"><span data-stu-id="7d9fc-148">Developing a Custom Cumulative Functoid</span></span>](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [<span data-ttu-id="7d9fc-149">Adición y eliminación de functoids personalizados del cuadro de herramientas de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d9fc-149">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d9fc-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d9fc-150">See Also</span></span>  
 [<span data-ttu-id="7d9fc-151">Uso de functoids para crear asignaciones más complejas</span><span class="sxs-lookup"><span data-stu-id="7d9fc-151">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)
---
title: Desarrollar Functoids personalizados | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77419e1f-9f01-44ac-bf5b-a393f1d17f61
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5534f3209cb943fb3e2c2a63a18f9e29928be5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-functoids"></a>Desarrollar Functoids personalizados
Aunque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona muchos functoids para admitir una gran cantidad de operaciones diferentes, probablemente se encontrará con una situación que requiera un enfoque distinto. Los functoids personalizados proporcionan una forma de ampliar la variedad de operaciones disponibles dentro del entorno de asignación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Cada functoid personalizado se implementa como un ensamblado .NET utilizando las clases derivadas de **Microsoft.BizTalk.BaseFunctoids**. Un ensamblado puede contener más de un functoid personalizado.  
  
 Debería considerar la posibilidad de utilizar un functoid personalizado en los escenarios siguientes:  
  
-   Existen reglas de conversión y validación especiales para un campo de código de carácter que utiliza datos a los que solo se puede obtener acceso a través de un API antiguo del propietario.  
  
-   Debe cifrar o descifrar campos mediante lógica empresarial personalizada y administración de claves.  
  
-   Necesita generar un código hash desde una parte del mensaje para utilizarlo en otra aplicación.  
  
-   Las solicitudes de administración de cuentas que transmitieron los mensajes a sus departamentos incluyen información de resumen acerca de ventas totales por cada tipo de producto.  
  
-   Si desea reducir la complejidad de una asignación, combine varios pasos relacionados, utilice un enfoque distinto o utilice bibliotecas de clases nuevas.  
  
-   Más de una asignación utiliza el mismo código de secuencia de comandos en un functoid de secuencia de comandos.  
  
-   Cuando se produce un error en una operación, lo debe escribir en el registro de eventos.  
  
 Los functoids personalizados se puede integrar en una solución directamente mediante un código en línea o, indirectamente, al hacer referencia a un método en una biblioteca de clases implementada en la caché de ensamblados global. Ambos tipos de integración se basan en el **BizTalk.BaseFunctoid** clase y siga el mismo conjunto de pasos generales:  
  
1.  Cree un proyecto de biblioteca de clases nueva mediante el lenguaje .NET que prefiera.  
  
2.  Mediante la utilidad de nombre seguro sn.exe, cree un keyfile y asígnelo al proyecto.  
  
3.  Agregue una referencia a Microsoft.BizTalk.BaseFunctoids.dll. Este ensamblado contiene el **BaseFunctoid** clase base.  
  
4.  Cree un archivo de recursos y agréguelo al proyecto. Agregue recursos de cadena para el nombre de functoid, la información sobre herramientas y la descripción. Agregue un recurso de imagen de 16 x 16 píxeles para representar el functoid en la paleta de diseñador de asignaciones.  
  
5.  Implementa la clase de functoid derivando de **BaseFunctoid**, establecer los parámetros básicos en el constructor y, a continuación, escribir el método de functoid y todos los métodos auxiliares. El ensamblado puede contener varios functoids personalizados.  
  
6.  Implemente el ensamblado y asegúrese de que el functoid nuevo está disponible de la paleta de Cuadro de herramientas. Vea [agregar y quitar Functoids personalizados del cuadro de herramientas de Visual Studio](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md).  
  
 A continuación se proporciona es una ilustración del functoid Floor.  
  
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
  
 Al usar este código de ejemplo como parte del proyecto de C#, el "Nombre de ensamblado" debe establecerse en "MultipleFunctoids". El proyecto de C# (que contiene este código) debe incluir un archivo Resource.resx.  
  
```  
SetName("NAME_FLOOR");  
SetDescription("DESCRIPTION_FLOOR");  
SetTooltip("DESCRIPTION_FLOOR");  
SetBitmap("IMAGE_FLOOR");  
  
```  
  
 En el código anterior, los valores "NAME_FLOOR", "DESCRIPTION_FLOOR" y "DESCRIPTION_FLOOR" son las "claves" de las cadenas de recursos incrustadas en el archivo Resource.resx. Además, "IMAGE_FLOOR" es el nombre de una imagen incrustada en el archivo Resource.resx. Esta imagen actuará como icono para el functoid.  
  
 Si no especifica claves de recursos adecuadas, o si elimina el método SetName, se creará un functoid personalizado sin nombre, lo cual no es un método recomendado. Lo mismo puede decirse de los métodos SetDescription y SetTooltip. Use siempre correctamente estos métodos para evitar un comportamiento de eliminación no deseado. No obstante, puede omitir el método SetBitmap si no tiene ninguna imagen adecuada para usar como iconos de functoid. En tal caso, el functoid personalizado usa un icono predeterminado, que es inocuo (a menos que haya varios functoids sin iconos).  
  
 Para obtener más información sobre cómo crear un functoid personalizado, consulte [Functoid personalizado (ejemplo de BizTalk Server)](../core/custom-functoid-biztalk-server-sample.md).  
  
> [!IMPORTANT]
>  Ciertos identificadores de functoid están reservados para functoids del Asignador estándar o integrados. Normalmente, los functoids del asignador estándares usan los identificadores de 1 a 10000. Al crear functoids personalizados, no use identificadores de functoid inferiores a 10.000.  
  
## <a name="in-this-section"></a>En esta sección  
 Esta sección contiene:  
  
-   [Utilizar BaseFunctoid](../core/using-basefunctoid.md)  
  
-   [Desarrollar un personalizado al que hace referencia de Functoid](../core/developing-a-custom-referenced-functoid.md)  
  
-   [Desarrollar un Functoid en línea personalizado](../core/developing-a-custom-inline-functoid.md)  
  
-   [Desarrollar un Functoid acumulado personalizado](../core/developing-a-custom-cumulative-functoid.md)  
  
-   [Agregar y quitar Functoids personalizados del cuadro de herramientas de Visual Studio](../core/adding-and-removing-custom-functoids-from-the-visual-studio-toolbox.md)  
  
## <a name="see-also"></a>Vea también  
 [Utilizar Functoids para crear asignaciones más complejas.](../core/using-functoids-to-create-more-complex-mappings.md)
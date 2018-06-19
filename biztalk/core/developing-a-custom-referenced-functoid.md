---
title: Desarrollar un personalizado al que hace referencia el Functoid | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e26d726-240c-4dfc-baa2-77451b8dc6c5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70f9cfcfaf50d92758f808346380b0a351a2f45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239228"
---
# <a name="developing-a-custom-referenced-functoid"></a><span data-ttu-id="efe93-102">Desarrollar un functoid personalizado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="efe93-102">Developing a Custom Referenced Functoid</span></span>
<span data-ttu-id="efe93-103">Los functoids personalizados a los que se hace referencia no copian el código de implementación interno en la asignación.</span><span class="sxs-lookup"><span data-stu-id="efe93-103">Custom referenced functoids do not copy implementation code inline into the map.</span></span> <span data-ttu-id="efe93-104">En lugar de ello, se coloca una referencia al ensamblado, la clase y el método en el archivo de objeto de extensión asociado con la hoja de estilos generada y se llama en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="efe93-104">Instead, a reference to the assembly, class, and method is placed in the extension object file associated with the generated style sheet and called at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efe93-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="efe93-105">Example</span></span>  
 <span data-ttu-id="efe93-106">El siguiente ejemplo ilustra cómo crear un functoid personalizado al que se hace referencia para la concatenación de dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="efe93-106">The following example illustrates how to create a custom referenced functoid for concatenating two strings.</span></span> <span data-ttu-id="efe93-107">Se basa en un archivo de recursos que contiene tres recursos de cadena y un recurso de mapa de bits de 16 x 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="efe93-107">It relies on a resource file containing three string resources and a 16x16-pixel bitmap resource.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.BaseFunctoids;  
using System.Reflection;  
  
namespace Microsoft.Samples.BizTalk.CustomFunctoid  
{  
    /// <summary>  
    /// Performs a string concatenation through assembly referenced function. Assembly must be deployed with the BizTalk solution.  
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
  
            // Set the function name that needs to be called  
            // when this functoid is invoked.  The resulting assembly  
            // must be present in the Global Assembly Cache  
            // to ensure its availability.  
            SetExternalFunctionName(GetType().Assembly.FullName, "Microsoft.Samples.BizTalk.CustomFunctoid.CustomStringConcatFunctoid", "ConCatStrings");  
        }  
  
        // This function is executed by BizTalk to do the concatenation  
        public string ConCatStrings(string val1, string val2)  
        {  
            return val2 + val1;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="efe93-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="efe93-108">See Also</span></span>  
 <span data-ttu-id="efe93-109">[Utilizar BaseFunctoid](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="efe93-109">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 <span data-ttu-id="efe93-110">[Desarrollar un Functoid en línea personalizado](../core/developing-a-custom-inline-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="efe93-110">[Developing a Custom Inline Functoid](../core/developing-a-custom-inline-functoid.md) </span></span>  
 <span data-ttu-id="efe93-111">[Desarrollar un Functoid acumulado personalizado](../core/developing-a-custom-cumulative-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="efe93-111">[Developing a Custom Cumulative Functoid](../core/developing-a-custom-cumulative-functoid.md) </span></span>  
 [<span data-ttu-id="efe93-112">Functoid personalizado (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="efe93-112">Custom Functoid (BizTalk Server Sample)</span></span>](../core/custom-functoid-biztalk-server-sample.md)
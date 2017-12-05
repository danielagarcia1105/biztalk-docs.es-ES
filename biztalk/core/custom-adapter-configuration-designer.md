---
title: "Diseñador de configuración de adaptador personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cff46f95062eff856653b6114f76f89ac17efd1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="custom-adapter-configuration-designer"></a><span data-ttu-id="0d433-102">Diseñador de configuración de adaptador personalizado</span><span class="sxs-lookup"><span data-stu-id="0d433-102">Custom Adapter Configuration Designer</span></span>
<span data-ttu-id="0d433-103">Deberá crear una biblioteca de clases .NET a partir de los diseñadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="0d433-103">You need to build the custom designers into a .NET class library.</span></span> <span data-ttu-id="0d433-104">Puede integrarlos al DLL del adaptador o crear un DLL distinto. </span><span class="sxs-lookup"><span data-stu-id="0d433-104">You may incorporate them into the DLL for the adapter or build a separate DLL.</span></span> <span data-ttu-id="0d433-105">Una vez creado un ensamblado de diseñador debe hacer referencia a él mediante decoraciones, como lo haría con una descripción o categoría.</span><span class="sxs-lookup"><span data-stu-id="0d433-105">After you build a designer assembly, you must reference it through decorations, just like a description or a category.</span></span> <span data-ttu-id="0d433-106">La referencia incluye una especificación del ensamblado y un nombre completo de clase para su uso.</span><span class="sxs-lookup"><span data-stu-id="0d433-106">The reference includes a specification of the assembly and a fully qualified class name to use.</span></span>  
  
 <span data-ttu-id="0d433-107">Estas decoraciones permiten dos maneras de hacer referencia al diseñador personalizado específico: como un ensamblado en la caché global de ensamblados global o como un ensamblado externo ubicado en el disco.</span><span class="sxs-lookup"><span data-stu-id="0d433-107">These decorations support two ways of referencing the specific custom designer: as a global assembly in the global assembly cache or as an external assembly located on the disk.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d433-108">Hay dos rutas de acceso de un ensamblado en tiempo de diseño posibles: puede especificar la ruta de acceso absoluta a los editores de tipo y los convertidores utilizados en la configuración de XSD en dicho XSD (no se admite la ruta de acceso relativa), o puede almacenar los convertidores y editores de tipo en la información global caché de ensamblados y necesita una ruta de acceso absoluta.</span><span class="sxs-lookup"><span data-stu-id="0d433-108">There are two possible design-time assembly paths: You can specify the absolute path to the type editors and converters used in the configuration XSD in the XSD itself (relative path is not supported), or you can store the type editors and converters in the global assembly cache and not need an absolute path.</span></span>  
  
## <a name="global-assembly-cache-designer-use"></a><span data-ttu-id="0d433-109">Uso del diseñador de la caché de ensamblados global</span><span class="sxs-lookup"><span data-stu-id="0d433-109">Global Assembly Cache Designer Use</span></span>  
 <span data-ttu-id="0d433-110">La caché de ensamblados global almacena ensamblados por nombre, clave pública, versión y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="0d433-110">The global assembly cache stores assemblies by assembly name, public key, version, and culture.</span></span> <span data-ttu-id="0d433-111">Por este motivo es recomendable:</span><span class="sxs-lookup"><span data-stu-id="0d433-111">Because of this, it is recommended that you:</span></span>  
  
1.  <span data-ttu-id="0d433-112">Generar un archivo de clave pública y agregarlo al archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="0d433-112">Generate a public key file and add this file to the AssemblyInfo.cs file.</span></span>  
  
2.  <span data-ttu-id="0d433-113">Especificar una versión específica en el archivo AssemblyInfo.cs.</span><span class="sxs-lookup"><span data-stu-id="0d433-113">Specify a specific version in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="0d433-114">Puede arrastrar el ensamblado hasta la caché de ensamblados global o usar GACUTIL para agregarlo a ella.</span><span class="sxs-lookup"><span data-stu-id="0d433-114">You can either drag the assembly into the global assembly cache or use GACUTIL to add it to the global assembly cache.</span></span>  
  
 <span data-ttu-id="0d433-115">Para usar este diseñador, especifique el nombre completo de clase, una coma y la entrada de la caché de ensamblados global (nombre de ensamblado, versión, referencia cultural y token de clave pública) como valor de la decoración.</span><span class="sxs-lookup"><span data-stu-id="0d433-115">To use this designer, specify the fully qualified class name, a comma, and the global assembly cache assembly entry (assembly name, version, culture, and public key token) as the value of the decoration.</span></span> <span data-ttu-id="0d433-116">Use \<editor\> decoraciones para **UITypeEditor** implementaciones y \<convertidor\> decoraciones para **TypeConverter** implementaciones .</span><span class="sxs-lookup"><span data-stu-id="0d433-116">Use \<editor\> decorations for **UITypeEditor** implementations and \<converter\> decorations for **TypeConverter** implementations.</span></span>  
  
 <span data-ttu-id="0d433-117">En el código siguiente se muestra cómo inicializar los diseñadores personalizados en un archivo XSD:</span><span class="sxs-lookup"><span data-stu-id="0d433-117">The following code shows how to initialize the custom designers in an XSD file:</span></span>  
  
```  
<xs:element name="Global" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>GAC Designer Component</baf:category>  
            <baf:editor>AdapterManagement.ComponentModel. PasswordUITypeEditor, AdapterManagement, Version=1.0.1.0, Culture=neutral, PublicKeyToken=f0db50abb0615c18</baf:editor>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
      </xs:sequence>  
```  
  
## <a name="external-assembly-installation-and-use"></a><span data-ttu-id="0d433-118">Instalación y uso de un ensamblado externo</span><span class="sxs-lookup"><span data-stu-id="0d433-118">External Assembly Installation and Use</span></span>  
 <span data-ttu-id="0d433-119">Para ensamblados externos, la decoración contiene un ensamblado de atributo opcional que especifica el nombre y ruta completos del ensamblado que contiene el diseñador deseado.</span><span class="sxs-lookup"><span data-stu-id="0d433-119">For external assemblies, the decoration contains an optional attribute assembly that specifies the full path and name of the assembly containing the desired designer.</span></span>  
  
 <span data-ttu-id="0d433-120">En el código siguiente se muestra cómo inicializar los diseñadores personalizados contenidos en ensamblados externos:</span><span class="sxs-lookup"><span data-stu-id="0d433-120">The following code shows how to initialize the custom designers contained in external assemblies:</span></span>  
  
```  
<xs:element name="External" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>External Designer Component</baf:category>  
            <baf:converter assembly="C:\source\private\Adapter\Framework\Designer\bin\Debug\Designer.External.dll">Designer.External.DesignerTypeConverter</baf:converter>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d433-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d433-121">See Also</span></span>  
 <span data-ttu-id="0d433-122">[Editor desplegable personalizado para la configuración del adaptador](../core/custom-drop-down-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d433-122">[Custom Drop-Down Editor for Adapter Configuration](../core/custom-drop-down-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="0d433-123">[Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d433-123">[Custom Modal Dialog Editor for Adapter Configuration](../core/custom-modal-dialog-editor-for-adapter-configuration.md) </span></span>  
 <span data-ttu-id="0d433-124">[Convertidor de tipos personalizado para la configuración del adaptador](../core/custom-type-converter-for-adapter-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0d433-124">[Custom Type Converter for Adapter Configuration](../core/custom-type-converter-for-adapter-configuration.md) </span></span>  
 [<span data-ttu-id="0d433-125">Componentes de configuración avanzada para adaptadores</span><span class="sxs-lookup"><span data-stu-id="0d433-125">Advanced Configuration Components for Adapters</span></span>](../core/advanced-configuration-components-for-adapters.md)
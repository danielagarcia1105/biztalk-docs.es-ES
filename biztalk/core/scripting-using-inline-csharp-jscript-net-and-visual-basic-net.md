---
title: Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, JScript
- Scripting functoids, warnings
- Scripting functoids, Visual Basic .NET
- Scripting functoids, inline C#
- Scripting functoids, .NET
ms.assetid: dda60024-58bd-483f-a750-31b21059eded
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2002bd92342a953406a21e076b801d3e90b938
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974546"
---
# <a name="scripting-using-inline-c-jscript-net-and-visual-basic-net"></a><span data-ttu-id="019e9-102">Secuencias de comandos que utilizan C#, JScript .NET y Visual Basic .NET en línea</span><span class="sxs-lookup"><span data-stu-id="019e9-102">Scripting Using Inline C#, JScript .NET, and Visual Basic .NET</span></span>
<span data-ttu-id="019e9-103">Las secuencias de comandos en línea son convenientes para el código personalizado que es poco probable que utilice en otra parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="019e9-103">Inline scripts are convenient for custom code that you are unlikely to use elsewhere in your application.</span></span>  
  
 <span data-ttu-id="019e9-104">BizTalk guarda las secuencias de comandos en línea en las hojas de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT) que definen la asignación.</span><span class="sxs-lookup"><span data-stu-id="019e9-104">BizTalk saves inline scripts in the Extensible Stylesheet Language Transformations (XSLT) stylesheet defining the map.</span></span> <span data-ttu-id="019e9-105">Debido a esto, las secuencias de comandos pueden utilizar el mismo espacio de nombres que cualquier otra secuencia de comandos de hojas de estilo XSLT.</span><span class="sxs-lookup"><span data-stu-id="019e9-105">Because of this, inline scripts may use the same namespaces as any other XSLT stylesheet script.</span></span> <span data-ttu-id="019e9-106">En la tabla siguiente se muestran los espacios de nombres disponibles.</span><span class="sxs-lookup"><span data-stu-id="019e9-106">The following table shows the available namespaces.</span></span>  
  
|<span data-ttu-id="019e9-107">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="019e9-107">Namespace</span></span>|<span data-ttu-id="019e9-108">Description</span><span class="sxs-lookup"><span data-stu-id="019e9-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="019e9-109">Sistema</span><span class="sxs-lookup"><span data-stu-id="019e9-109">System</span></span>|<span data-ttu-id="019e9-110">La clase System.</span><span class="sxs-lookup"><span data-stu-id="019e9-110">The System class.</span></span>|  
|<span data-ttu-id="019e9-111">System.Collection</span><span class="sxs-lookup"><span data-stu-id="019e9-111">System.Collection</span></span>|<span data-ttu-id="019e9-112">Las clases de colección.</span><span class="sxs-lookup"><span data-stu-id="019e9-112">The collection classes.</span></span>|  
|<span data-ttu-id="019e9-113">System.Text</span><span class="sxs-lookup"><span data-stu-id="019e9-113">System.Text</span></span>|<span data-ttu-id="019e9-114">Las clases de texto.</span><span class="sxs-lookup"><span data-stu-id="019e9-114">The text classes.</span></span>|  
|<span data-ttu-id="019e9-115">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="019e9-115">System.Text.RegularExpressions</span></span>|<span data-ttu-id="019e9-116">Las clases de expresiones regulares.</span><span class="sxs-lookup"><span data-stu-id="019e9-116">The regular expression classes.</span></span>|  
|<span data-ttu-id="019e9-117">System.Xml</span><span class="sxs-lookup"><span data-stu-id="019e9-117">System.Xml</span></span>|<span data-ttu-id="019e9-118">Las clases XML principales.</span><span class="sxs-lookup"><span data-stu-id="019e9-118">The core XML classes.</span></span>|  
|<span data-ttu-id="019e9-119">System.Xml.Xsl</span><span class="sxs-lookup"><span data-stu-id="019e9-119">System.Xml.Xsl</span></span>|<span data-ttu-id="019e9-120">Las clases XSLT.</span><span class="sxs-lookup"><span data-stu-id="019e9-120">The XSLT classes.</span></span>|  
|<span data-ttu-id="019e9-121">System.Xml.Xpath</span><span class="sxs-lookup"><span data-stu-id="019e9-121">System.Xml.Xpath</span></span>|<span data-ttu-id="019e9-122">Las clases XPath.</span><span class="sxs-lookup"><span data-stu-id="019e9-122">The XPath classes.</span></span>|  
|<span data-ttu-id="019e9-123">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="019e9-123">Microsoft.VisualBasic</span></span>|<span data-ttu-id="019e9-124">Las clases de secuencias de comandos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="019e9-124">The Visual Basic script classes.</span></span>|  
  
 <span data-ttu-id="019e9-125">Para obtener más información acerca de los espacios de nombres y tipos de datos, busque "uso de secuencias de comandos de hojas de estilo XSLT \<msxsl: script\>" y "System.Xml.Xsl.XslCompiledTransform" en la colección de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="019e9-125">For more information about namespaces and data types, search on "XSLT Stylesheet Scripting using \<msxsl:script\>" and on "System.Xml.Xsl.XslCompiledTransform" in the .NET Framework collection.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="019e9-126">Evite utilizar la misma firma de método más de una vez.</span><span class="sxs-lookup"><span data-stu-id="019e9-126">Avoid using the same method signature more than once.</span></span> <span data-ttu-id="019e9-127">Cuando varios functoids de secuencia de comandos tienen la misma firma de método, BizTalk selecciona la primera implementación y descarta las otras.</span><span class="sxs-lookup"><span data-stu-id="019e9-127">When several Scripting functoids have the same method signature, BizTalk selects the first implementation and disregards the others.</span></span>  
  
 <span data-ttu-id="019e9-128">Además de ser útiles para las secuencias de comandos que sólo se utilizan una vez, las secuencias de comandos también son prácticas para declarar variables globales que van a utilizar una serie de secuencias de comandos.</span><span class="sxs-lookup"><span data-stu-id="019e9-128">In addition to being convenient for one-time scripts, inline scripts are also useful for declaring global variables for use among a number of scripts.</span></span> <span data-ttu-id="019e9-129">Por ejemplo, en una secuencia de comandos en línea C#, podría poner la siguiente línea de código fuera de cualquier clase.</span><span class="sxs-lookup"><span data-stu-id="019e9-129">For example, in a C# inline script, you could place the following line of code outside of any class.</span></span>  
  
```  
ArrayList statusList = new ArrayList();  
```  
  
 <span data-ttu-id="019e9-130">Esto crea una **ArrayList**, `statusList`, que está disponible para todas las secuencias de comandos en el mapa.</span><span class="sxs-lookup"><span data-stu-id="019e9-130">This creates an **ArrayList**, `statusList`, available to all inline scripts in the map.</span></span>  
  
 <span data-ttu-id="019e9-131">Para una secuencia de comandos de ejemplo en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).</span><span class="sxs-lookup"><span data-stu-id="019e9-131">For a sample inline script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019e9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="019e9-132">See Also</span></span>  
 <span data-ttu-id="019e9-133">[Secuencias de comandos de Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="019e9-133">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="019e9-134">[Secuencias de comandos con ensamblados externos](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="019e9-134">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="019e9-135">[Secuencias de comandos utilizando XSLT en línea y plantillas de llamada XSLT](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span><span class="sxs-lookup"><span data-stu-id="019e9-135">[Scripting Using Inline XSLT and XSLT Call Templates](../core/scripting-using-inline-xslt-and-xslt-call-templates.md) </span></span>  
 <span data-ttu-id="019e9-136">[Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="019e9-136">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="019e9-137">Cómo configurar el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="019e9-137">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)
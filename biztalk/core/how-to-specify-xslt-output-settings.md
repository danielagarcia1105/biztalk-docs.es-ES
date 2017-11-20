---
title: "Opciones de salida de cómo especificar XSLT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c541432-fd4e-41cc-8bcc-f570ce5df439
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1aa3eea4c3f2f4696d3dc1fdf8109aeddec3ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="set-map-compilation-and-output-settings"></a><span data-ttu-id="ec657-102">Establezca la compilación del mapa y opciones de salida</span><span class="sxs-lookup"><span data-stu-id="ec657-102">Set map compilation and output settings</span></span>
<span data-ttu-id="ec657-103">Establecer las propiedades de asignación en el asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="ec657-103">Set the map properties in the BizTalk mapper.</span></span> 

<span data-ttu-id="ec657-104">Uso de estas propiedades de asignación, puede establecer cómo se compilan los mapas, incluir o excluir una declaración XML y el codificador del juego.</span><span class="sxs-lookup"><span data-stu-id="ec657-104">Using these map properties, you can set how maps are compiled, include or exclude an XML declaration, and set the encoding.</span></span> 

<span data-ttu-id="ec657-105">En este tema se muestra cómo establecer estas propiedades en el mapa.</span><span class="sxs-lookup"><span data-stu-id="ec657-105">This topic shows you how to set these properties on your map.</span></span>

## <a name="set-the-map-level-compilation"></a><span data-ttu-id="ec657-106">Establezca la compilación de nivel de asignación</span><span class="sxs-lookup"><span data-stu-id="ec657-106">Set the map-level compilation</span></span>

<span data-ttu-id="ec657-107">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** , elige el `XslTransform` o `XslCompiledTransform` clase para compilar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="ec657-107">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you choose the `XslTransform` or the `XslCompiledTransform` class to compile your maps.</span></span> 

1. <span data-ttu-id="ec657-108">Abra la asignación en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ec657-108">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="ec657-109">Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec657-109">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="ec657-110">Establecer el **Use la opción Transformar XSL** propiedad:</span><span class="sxs-lookup"><span data-stu-id="ec657-110">Set the **Use XSL Transform** property:</span></span> 

    | <span data-ttu-id="ec657-111">Opción</span><span class="sxs-lookup"><span data-stu-id="ec657-111">Option</span></span> | <span data-ttu-id="ec657-112">Description</span><span class="sxs-lookup"><span data-stu-id="ec657-112">Description</span></span> |
    | --- | --- |
    | <span data-ttu-id="ec657-113">No definido</span><span class="sxs-lookup"><span data-stu-id="ec657-113">Undefined</span></span> | <span data-ttu-id="ec657-114">Se utiliza la marca de registro para la configuración de XslTransform:</span><span class="sxs-lookup"><span data-stu-id="ec657-114">The registry flag for the XslTransform setting is used:</span></span> <ul><li><span data-ttu-id="ec657-115">instancias de host de 64 bits:`HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="ec657-115">64-bit host instances: `HKLM\SOFTWARE\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li><li><span data-ttu-id="ec657-116">instancias de host de 32 bits y la funcionalidad de mapas de prueba de Visual Studio:`HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span><span class="sxs-lookup"><span data-stu-id="ec657-116">32-bit host instances, and Visual Studio’s Test Map functionality: `HKLM\SOFTWARE\Wow6432Node\Microsoft\BizTalk Server\3.0\Configuration`</span></span></li></ul> | 
    | <span data-ttu-id="ec657-117">True</span><span class="sxs-lookup"><span data-stu-id="ec657-117">True</span></span> | <span data-ttu-id="ec657-118">La propiedad de compilación de nivel de asignación se establece en `XslTransform` (comportamiento heredado)</span><span class="sxs-lookup"><span data-stu-id="ec657-118">The map level compilation property is set to `XslTransform` (legacy behavior)</span></span> | 
    | <span data-ttu-id="ec657-119">False</span><span class="sxs-lookup"><span data-stu-id="ec657-119">False</span></span> | <span data-ttu-id="ec657-120">La propiedad de compilación de nivel de asignación se establece en`XslCompiledTransform`</span><span class="sxs-lookup"><span data-stu-id="ec657-120">The map level compilation property is set to `XslCompiledTransform`</span></span> | 

> [!NOTE] 
> <span data-ttu-id="ec657-121">A partir de BizTalk Server 2013, se cambió el comportamiento de compilación de asignador de `XslTransform` a `XslCompiledTransform`.</span><span class="sxs-lookup"><span data-stu-id="ec657-121">Starting with BizTalk Server 2013, the mapper compilation behavior was changed from `XslTransform` to `XslCompiledTransform`.</span></span> <span data-ttu-id="ec657-122">El [el asignador de actualizaciones significado para usted](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) entrada de blog proporciona una explicación excelente del comportamiento y el impacto potencial.</span><span class="sxs-lookup"><span data-stu-id="ec657-122">The [What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/) blog post provides a great explanation of the behavior, and its potential impact.</span></span> 
> 
> <span data-ttu-id="ec657-123">A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], puede elegir qué clase se debe compilar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="ec657-123">Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], you can choose which class to compile your maps.</span></span> 
  
## <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="ec657-124">Incluir o excluir una declaración XML</span><span class="sxs-lookup"><span data-stu-id="ec657-124">Include or exclude an XML declaration</span></span>  
<span data-ttu-id="ec657-125">Puede elegir si una declaración XML es la salida o no.</span><span class="sxs-lookup"><span data-stu-id="ec657-125">You can choose whether an XML declaration is output or not.</span></span> 

1. <span data-ttu-id="ec657-126">Abra la asignación en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ec657-126">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="ec657-127">Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec657-127">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>  
3. <span data-ttu-id="ec657-128">En la lista desplegable para la **omitir declaración XML** propiedad, seleccione **Sí** para omitir una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="ec657-128">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration.</span></span> <span data-ttu-id="ec657-129">Seleccione **No** no para omitir una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="ec657-129">Select **No** not to omit an XML declaration.</span></span>  

<span data-ttu-id="ec657-130">Aparecerá una declaración XML (si seleccionó **n**) similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="ec657-130">An XML declaration would appear (if you selected **No**) similar to the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
```  
  
## <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="ec657-131">Establecer la codificación de datos de instancia de salida</span><span class="sxs-lookup"><span data-stu-id="ec657-131">Set encoding for output instance data</span></span>  
<span data-ttu-id="ec657-132">La codificación proporciona al motor en tiempo de ejecución la información que necesita para determinar qué juego de caracteres utilizar cuando cree el resultado de salida de una asignación.</span><span class="sxs-lookup"><span data-stu-id="ec657-132">Encoding provides the run-time engine with the information it needs to determine which character set to use when creating the output result of a map.</span></span>  
   
1. <span data-ttu-id="ec657-133">Abra la asignación en la vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ec657-133">Open your map in the Grid view.</span></span>
2. <span data-ttu-id="ec657-134">Haga clic en cualquier lugar en la cuadrícula del asignador y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec657-134">Right-click anywhere in the mapper grid, and select **Properties**.</span></span>    
3.  <span data-ttu-id="ec657-135">En la lista desplegable para la **codificación XSLT** propiedad, seleccione el juego de caracteres desea usar para los datos de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="ec657-135">In the drop-down list for the **XSLT Encoding** property, select the character set you want used for the output instance data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec657-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec657-136">See Also</span></span>  
 <span data-ttu-id="ec657-137">[Compilar y probar las asignaciones](../core/compiling-and-testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="ec657-137">[Compiling and Testing Maps](../core/compiling-and-testing-maps.md) </span></span>  
 <span data-ttu-id="ec657-138">[Con el asignador de BizTalk](../core/using-biztalk-mapper.md) </span><span class="sxs-lookup"><span data-stu-id="ec657-138">[Using BizTalk Mapper](../core/using-biztalk-mapper.md) </span></span>  
 [<span data-ttu-id="ec657-139">XSLT en el asignador de BizTalk válido tipos de codificación</span><span class="sxs-lookup"><span data-stu-id="ec657-139">Valid BizTalk Mapper XSLT Encoding Types</span></span>](../core/valid-biztalk-mapper-xslt-encoding-types.md)
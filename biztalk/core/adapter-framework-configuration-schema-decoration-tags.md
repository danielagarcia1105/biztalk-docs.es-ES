---
title: "Etiquetas de decoración de esquema de configuración de adaptador Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d5d7f6b-2273-45a6-ba9d-43201760cf22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834482b70e75d12bb6786dac2a5d9eb6f9fef40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-decoration-tags"></a><span data-ttu-id="be05b-102">Etiquetas de decoración de esquema de configuración de adaptador Framework</span><span class="sxs-lookup"><span data-stu-id="be05b-102">Adapter Framework Configuration Schema Decoration Tags</span></span>
<span data-ttu-id="be05b-103">Las etiquetas que se describen en este tema se pueden usar en los archivos de esquema de configuración para que los datos se muestren y organicen en las páginas de propiedades de adaptador.</span><span class="sxs-lookup"><span data-stu-id="be05b-103">You can use the tags described in this topic within the configuration schema files to display and organize data on the adapter property pages.</span></span>  
  
 <span data-ttu-id="be05b-104">En la ilustración siguiente se muestra cómo la página de propiedades de la ubicación de recepción de FTP implementa algunas de estas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="be05b-104">The following figure shows how the FTP receive location property page implements some of these tags.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-tags.gif "ebiz_prog_custad_tags")  
<span data-ttu-id="be05b-105">El \<descripción >, \<displayname >, y \<categoría > etiquetas en la página de propiedades del adaptador FTP</span><span class="sxs-lookup"><span data-stu-id="be05b-105">The \<description>, \<displayname>, and \<category> tags in the FTP adapter property page</span></span>  
  
## <a name="designer"></a><span data-ttu-id="be05b-106">\<Diseñador ></span><span class="sxs-lookup"><span data-stu-id="be05b-106">\<designer></span></span>  
 <span data-ttu-id="be05b-107">La decoración de adaptador de BizTalk Framework aparece entre un \<Designer > etiqueta y \</baf:designer > etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="be05b-107">The BizTalk Adapter Framework decorations appear between a \<baf:designer> tag and \</baf:designer> end tag.</span></span> <span data-ttu-id="be05b-108">El \<Designer > tag ayuda a distinguir entre el marco de trabajo \<appinfo > y otros suministrada por el adaptador \<appinfo > información.</span><span class="sxs-lookup"><span data-stu-id="be05b-108">The \<baf:designer> tag helps distinguish between Adapter Framework \<appinfo> and other adapter-supplied \<appinfo> information.</span></span>  
  
## <a name="category"></a><span data-ttu-id="be05b-109">\<categoría ></span><span class="sxs-lookup"><span data-stu-id="be05b-109">\<category></span></span>  
 <span data-ttu-id="be05b-110">El \<categoría > decoración contiene la cadena utilizada para separar las entradas de la cuadrícula de propiedades en grupos.</span><span class="sxs-lookup"><span data-stu-id="be05b-110">The \<category> decoration contains the string used to separate entries in the property grid into groups.</span></span> <span data-ttu-id="be05b-111">La decoración muestra todas las entradas con la misma cadena de categoría como las cadenas subordinadas de la categoría.</span><span class="sxs-lookup"><span data-stu-id="be05b-111">The decoration displays all entries with the same category string as subordinate entries of the category.</span></span>  
  
 <span data-ttu-id="be05b-112">Puede localizar \<categoría > entradas.</span><span class="sxs-lookup"><span data-stu-id="be05b-112">You can localize \<category> entries.</span></span>  
  
## <a name="description"></a><span data-ttu-id="be05b-113">\<Descripción ></span><span class="sxs-lookup"><span data-stu-id="be05b-113">\<description></span></span>  
 <span data-ttu-id="be05b-114">El \<descripción > decoración contiene la cadena utilizada para proporcionar texto descriptivo para las entradas en la parte inferior de la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="be05b-114">The \<description> decoration contains the string used to provide descriptive text for entries at the bottom of the property grid.</span></span>  
  
 <span data-ttu-id="be05b-115">Puede localizar \<descripción > entradas.</span><span class="sxs-lookup"><span data-stu-id="be05b-115">You can localize \<description> entries.</span></span>  
  
## <a name="displayname"></a><span data-ttu-id="be05b-116">\<DisplayName ></span><span class="sxs-lookup"><span data-stu-id="be05b-116">\<displayname></span></span>  
 <span data-ttu-id="be05b-117">El \<displayname > decoración contiene la cadena utilizada para mostrar el nombre de una entrada.</span><span class="sxs-lookup"><span data-stu-id="be05b-117">The \<displayname> decoration contains the string used for displaying the name of an entry.</span></span> <span data-ttu-id="be05b-118">Esto le permite usar espacios, frases y así sucesivamente, cuando no se permitirá para un \<elemento > o \<atributo > nombre.</span><span class="sxs-lookup"><span data-stu-id="be05b-118">This enables you to use spaces, phrases, and so on, when they would not be allowed for an \<element> or \<attribute> name.</span></span>  
  
 <span data-ttu-id="be05b-119">Puede localizar \<displayname > entradas.</span><span class="sxs-lookup"><span data-stu-id="be05b-119">You can localize \<displayname> entries.</span></span>  
  
## <a name="readonly"></a><span data-ttu-id="be05b-120">\<ReadOnly ></span><span class="sxs-lookup"><span data-stu-id="be05b-120">\<readonly></span></span>  
 <span data-ttu-id="be05b-121">El \<readonly fijada = "" > decoración controla si un campo se puede editar.</span><span class="sxs-lookup"><span data-stu-id="be05b-121">The \<readonly fixed=""> decoration controls whether a field may be edited.</span></span> <span data-ttu-id="be05b-122">El valor del atributo "fixed" `true` (predeterminado) hace que un campo sea de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="be05b-122">A "fixed" attribute value of `true` (the default) makes a field read-only.</span></span>  
  
 <span data-ttu-id="be05b-123">Al implementar un editor externo, implemente una referencia externa **TypeConverter** clase e invalidar el **GetStandardValuesExclusive** método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="be05b-123">When implementing an external editor, implement an external **TypeConverter** class and override the **GetStandardValuesExclusive(ITypeDescriptorContext)** method instead.</span></span> <span data-ttu-id="be05b-124">La devolución de `true` hace que un campo sea de solo lectura pero mantiene el acceso al editor personalizado.</span><span class="sxs-lookup"><span data-stu-id="be05b-124">Returning `true` makes a field read-only but preserves access to the custom editor.</span></span>  
  
## <a name="browsable"></a><span data-ttu-id="be05b-125">\<puede examinar ></span><span class="sxs-lookup"><span data-stu-id="be05b-125">\<browsable></span></span>  
 <span data-ttu-id="be05b-126">El \<browsable show = "" > decoración controla si un campo aparece en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="be05b-126">The \<browsable show=""> decoration controls whether a field appears in the property grid.</span></span> <span data-ttu-id="be05b-127">Valor de atributo de un "Mostrar" `True` (valor predeterminado) hace que el campo aparecen en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="be05b-127">A "show" attribute value of `True` (the default) makes a field appear in the grid.</span></span>  
  
## <a name="converter"></a><span data-ttu-id="be05b-128">\<convertidor ></span><span class="sxs-lookup"><span data-stu-id="be05b-128">\<converter></span></span>  
 <span data-ttu-id="be05b-129">El \<ensamblado convertidor = "" > decoración especifica lo que se desea **TypeConverter** nombre de clase para la \<elemento > o \<atributo >.</span><span class="sxs-lookup"><span data-stu-id="be05b-129">The \<converter assembly=""> decoration specifies the desired **TypeConverter** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="be05b-130">El valor del atributo "assembly" opcional especifica la ruta de acceso al ensamblado que contiene lo que se desea **TypeConverter**.</span><span class="sxs-lookup"><span data-stu-id="be05b-130">The optional "assembly" attribute value specifies the path to the assembly containing the desired **TypeConverter**.</span></span> <span data-ttu-id="be05b-131">Sin un valor de "assembly" especificado, el nombre de la clase debe incluir los valores de nombre del ensamblado de la caché de ensamblados global, la clave, la referencia cultural y la versión.</span><span class="sxs-lookup"><span data-stu-id="be05b-131">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="editor"></a><span data-ttu-id="be05b-132">\<Editor de ></span><span class="sxs-lookup"><span data-stu-id="be05b-132">\<editor></span></span>  
 <span data-ttu-id="be05b-133">El \<ensamblado editor = "" > decoración especifica lo que se desea **UITypeEditor** nombre de clase para la \<elemento > o \<atributo >.</span><span class="sxs-lookup"><span data-stu-id="be05b-133">The \<editor assembly=""> decoration specifies the desired **UITypeEditor** class name for the \<element> or \<attribute>.</span></span> <span data-ttu-id="be05b-134">El valor del atributo "assembly" opcional especifica la ruta de acceso al ensamblado que contiene lo que se desea **UITypeEditor**.</span><span class="sxs-lookup"><span data-stu-id="be05b-134">The optional "assembly" attribute value specifies the path to the assembly containing the desired **UITypeEditor**.</span></span> <span data-ttu-id="be05b-135">Sin un valor de "assembly" especificado, el nombre de la clase debe incluir los valores de nombre del ensamblado de la caché de ensamblados global, la clave, la referencia cultural y la versión.</span><span class="sxs-lookup"><span data-stu-id="be05b-135">With no "assembly" value specified, the class name must include the global assembly cache's assembly name, key, culture, and version values.</span></span>  
  
## <a name="null-values-for-optional-enumerations"></a><span data-ttu-id="be05b-136">Valores nulos para enumeraciones opcionales</span><span class="sxs-lookup"><span data-stu-id="be05b-136">Null Values for Optional Enumerations</span></span>  
 <span data-ttu-id="be05b-137">Al usar una enumeración opcional, debe tener uno de los valores \<ninguno > para indicar un valor nulo.</span><span class="sxs-lookup"><span data-stu-id="be05b-137">When using an optional enumeration, one of the values should be \<none> to denote a null value.</span></span> <span data-ttu-id="be05b-138">No se trata de una etiqueta integrada aunque se puede conseguir al proporcionar un valor de enumeración que se trate como ninguno si la enumeración se deriva desde xsd:string.</span><span class="sxs-lookup"><span data-stu-id="be05b-138">This is not a built-in tag, but may be achieved by providing an enumeration value that is treated as none if the enumeration is derived from xsd:string.</span></span> <span data-ttu-id="be05b-139">Esto no es posible para las enumeraciones que se derivan desde xsd:int, ya que el entero debe contener un valor.</span><span class="sxs-lookup"><span data-stu-id="be05b-139">This is not possible for enumerations derived from xsd:int, because the integer must hold a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be05b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="be05b-140">See Also</span></span>  
 [<span data-ttu-id="be05b-141">Extensiones de esquema de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="be05b-141">Adapter Framework Configuration Schema Extensions</span></span>](../core/adapter-framework-configuration-schema-extensions.md)
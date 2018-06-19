---
title: Secuencias de comandos mediante XSLT en línea y plantillas de llamada XSLT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270436"
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a><span data-ttu-id="53573-102">Crear secuencias de comandos mediante XSLT en línea y plantillas de llamada XSLT en línea</span><span class="sxs-lookup"><span data-stu-id="53573-102">Scripting Using Inline XSLT and XSLT Call Templates</span></span>
<span data-ttu-id="53573-103">Puede escribir directamente hojas de estilos Extensible Stylesheet Language Transformations (XSLT) para su uso en el **secuencias de comandos** functoid.</span><span class="sxs-lookup"><span data-stu-id="53573-103">You can directly write Extensible Stylesheet Language Transformations (XSLT) stylesheets for use in the **Scripting** functoid.</span></span> <span data-ttu-id="53573-104">Esto le permite realizar transformaciones que tal vez los vínculos y functoids integrados no sean capaces de representar.</span><span class="sxs-lookup"><span data-stu-id="53573-104">This enables you to perform transformations, that links and built-in functoids may not be able to represent.</span></span> <span data-ttu-id="53573-105">Hay dos tipos de secuencias de comandos XSLT: en línea plantillas de llamada XSLT y XSLT.</span><span class="sxs-lookup"><span data-stu-id="53573-105">There are two kinds of XSLT scripts: inline XSLT and XSLT call templates.</span></span> <span data-ttu-id="53573-106">Cuando selecciona una de ellas en el **Seleccionar tipo de script** lista desplegable en el **configurar Functoid de script** cuadro de diálogo, aparece el código de ejemplo que puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="53573-106">When you select either in the **Select script type** dropdown in the **Configure Scripting Functoid** dialog box, sample code appears that you may use.</span></span>  
  
 <span data-ttu-id="53573-107">Las plantillas de secuencias de comandos XSLT en línea y llamada XSLT en línea pueden llamar funciones en ensamblados externos.</span><span class="sxs-lookup"><span data-stu-id="53573-107">Inline XSLT scripts and inline XSLT call templates may call functions in external assemblies.</span></span> <span data-ttu-id="53573-108">Para realizar esas llamadas requiere la configuración del **XML de extensión personalizada** propiedad de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="53573-108">Making such calls requires setting the **Custom Extension XML** property of the grid.</span></span> <span data-ttu-id="53573-109">Para obtener más información, consulte **XML de extensión personalizada (propiedad de cuadrícula)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="53573-109">For more information, see **Custom Extension XML (Grid Property)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="inline-xslt"></a><span data-ttu-id="53573-110">XSLT en línea</span><span class="sxs-lookup"><span data-stu-id="53573-110">Inline XSLT</span></span>  
 <span data-ttu-id="53573-111">Una secuencia de comandos XSLT en línea solo puede producir salidas.</span><span class="sxs-lookup"><span data-stu-id="53573-111">An inline XSLT script may only produce output.</span></span> <span data-ttu-id="53573-112">El **secuencias de comandos** functoid no puede tener vínculos de entrada.</span><span class="sxs-lookup"><span data-stu-id="53573-112">The **Scripting** functoid may not have any input links.</span></span> <span data-ttu-id="53573-113">El functoid también debe vincular directamente a un registro o campo en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="53573-113">The functoid must also directly link to a record or field in the destination schema.</span></span>  
  
 <span data-ttu-id="53573-114">Además, la secuencia de comandos es responsable de la creación del nodo de destino y cualquier estructura que esté debajo de él.</span><span class="sxs-lookup"><span data-stu-id="53573-114">In addition, the script is responsible for creating the target node and any structures underneath it.</span></span>  
  
 <span data-ttu-id="53573-115">El siguiente mensaje de instancia de entrada contiene dos elementos que representan información de contacto.</span><span class="sxs-lookup"><span data-stu-id="53573-115">The following input instance message contains two elements representing contact information.</span></span>  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 <span data-ttu-id="53573-116">El siguiente script XSLT en línea, en el búfer de secuencia de comandos, convierte el **póngase en contacto con** y **ContactType** campos a los atributos.</span><span class="sxs-lookup"><span data-stu-id="53573-116">The following inline XSLT script, entered in the script buffer, converts the **Contact** and **ContactType** fields to attributes.</span></span>  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 <span data-ttu-id="53573-117">La secuencia de comandos crea la siguiente salida, suponiendo que el esquema de salida sea el adecuado, cuando se ejecuta con respecto al mensaje de instancia de entrada anterior.</span><span class="sxs-lookup"><span data-stu-id="53573-117">The script produces the following output, assuming an appropriate output schema, when run against the preceding input instance message.</span></span>  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 <span data-ttu-id="53573-118">Tenga en cuenta que la ausencia de vínculos a la **secuencias de comandos** functoid no impide que la secuencia de comandos XSLT obtener datos desde el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="53573-118">Notice that the absence of links to the **Scripting** functoid does not prevent the XSLT script from getting data from the input instance message.</span></span> <span data-ttu-id="53573-119">La secuencia de comandos especifica rutas a los valores de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="53573-119">The script specifies paths to the input instance values.</span></span>  
  
 <span data-ttu-id="53573-120">Para obtener otro ejemplo de una secuencia de comandos XSLT en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).</span><span class="sxs-lookup"><span data-stu-id="53573-120">For another example of an inline XSLT script, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="inline-xslt-call-templates"></a><span data-ttu-id="53573-121">Plantillas de llamada XSLT en línea</span><span class="sxs-lookup"><span data-stu-id="53573-121">Inline XSLT Call Templates</span></span>  
 <span data-ttu-id="53573-122">Al igual que una secuencia de comandos XSLT en línea, una plantilla de llamada XSLT en línea debe conectar directamente con un nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="53573-122">Like an inline XSLT script, an inline XSLT call template must connect directly to a destination node.</span></span> <span data-ttu-id="53573-123">Sin embargo, una plantilla de llamada XSLT en línea puede utilizar vínculos del esquema de origen y de otros functoids.</span><span class="sxs-lookup"><span data-stu-id="53573-123">However, an inline XSLT call template may use links from the source schema and from other functoids.</span></span>  
  
 <span data-ttu-id="53573-124">La plantilla de llamada es responsable de la creación del nodo de destino y todas sus subestructuras.</span><span class="sxs-lookup"><span data-stu-id="53573-124">The call template is responsible for creating the destination node and any of its substructures.</span></span>  
  
 <span data-ttu-id="53573-125">Aparece una plantilla de llamada XSLT de ejemplo que concatena dos elementos en el **de entrada de secuencia de comandos** almacenar en búfer cuando se selecciona **plantilla de llamada de XSLT en línea** en el **Seleccionar tipo de script** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="53573-125">A sample XSLT call template that concatenates two elements appears in the **Input script** buffer when you select **Inline XSLT Call Template** in the **Select script type** dropdown.</span></span>  
  
 <span data-ttu-id="53573-126">Para obtener otro ejemplo de una plantilla de llamada XSLT en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).</span><span class="sxs-lookup"><span data-stu-id="53573-126">For another example of an inline XSLT call template, see [XML Tools (BizTalk Server Samples Folder)](../core/xml-tools-biztalk-server-samples-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53573-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="53573-127">See Also</span></span>  
 <span data-ttu-id="53573-128">[Secuencias de comandos de Functoid](../core/scripting-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="53573-128">[Scripting Functoid](../core/scripting-functoid.md) </span></span>  
 <span data-ttu-id="53573-129">[Secuencias de comandos con ensamblados externos](../core/scripting-using-external-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="53573-129">[Scripting Using External Assemblies](../core/scripting-using-external-assemblies.md) </span></span>  
 <span data-ttu-id="53573-130">[Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span><span class="sxs-lookup"><span data-stu-id="53573-130">[Scripting Using Inline C#, JScript .NET, and Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md) </span></span>  
 <span data-ttu-id="53573-131">[Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="53573-131">[How to Add Scripting Functoids to a Map](../core/how-to-add-scripting-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="53573-132">Cómo configurar el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="53573-132">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)
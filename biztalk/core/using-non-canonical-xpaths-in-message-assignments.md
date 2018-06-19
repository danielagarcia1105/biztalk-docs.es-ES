---
title: Usar XPaths no canónicos en las asignaciones de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 052d1d72-43ce-4654-bf29-86f82ad65e91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201d6f8b6bc910faf79b64ac0b4617530b20608a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287628"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a><span data-ttu-id="7b6a7-102">Usar XPaths no canónicos en las asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="7b6a7-102">Using Non-Canonical XPaths in Message Assignments</span></span>
<span data-ttu-id="7b6a7-103">Si se utilizan partes de mensaje de .Net, es posible anotar el código con el atributo de serialización XML que, cuando también se acompaña con anotaciones de propiedad o campos distintivos, puede tener como resultado expresiones de XPath de considerable complejidad.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-103">If you use .Net message parts, it is possible to annotate your code with the XML serialization attribute that, when also accompanied by distinguished fields and/or property annotations, can result in fairly complex XPath expressions.</span></span> <span data-ttu-id="7b6a7-104">Es posible que estas expresiones complejas de XPath sean no canónicas.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-104">It is possible that these complex XPath expressions will be non-canonical.</span></span> <span data-ttu-id="7b6a7-105">solo se debería utilizar XPath no canónico en orquestaciones de enlace directo; es posible que se produzcan errores con orquestaciones enlazadas lógica o físicamente.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-105">Non-canonical XPath should only be used in direct bound orchestrations and may fail with logically or physically bound orchestrations.</span></span> <span data-ttu-id="7b6a7-106">Las orquestaciones de enlace directo no se basan en una canalización para procesar el documento XML; en consecuencia, todo el documento XML se carga en la memoria antes del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-106">Direct bound orchestrations do not rely on a pipeline for processing the XML document; as a result, the entire XML document is loaded in memory prior to processing.</span></span>  
  
## <a name="canonical-and-non-canonical-xpath"></a><span data-ttu-id="7b6a7-107">XPath canónico y no canónico</span><span class="sxs-lookup"><span data-stu-id="7b6a7-107">Canonical and Non-Canonical XPath</span></span>  
 <span data-ttu-id="7b6a7-108">La forma abreviada de XPath o canónico utiliza la sintaxis abreviada de la especificación de XPath ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) para especificar una ruta de acceso de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-108">The canonical or short-form of XPath uses the abbreviated syntax from the XPath specification ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) to specify a location path.</span></span> <span data-ttu-id="7b6a7-109">Entre las propiedades distintivas de expresiones de XPath canónico se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-109">Some distinguishing properties of canonical XPath expressions include:</span></span>  
  
-   <span data-ttu-id="7b6a7-110">El `child::` eje se establece como valor predeterminado para cada paso de la expresión</span><span class="sxs-lookup"><span data-stu-id="7b6a7-110">The `child::` axis is assumed by default for each step of the expression</span></span>  
  
-   <span data-ttu-id="7b6a7-111">`@`es una abreviación de `attribute::`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-111">`@` is short for `attribute::`.</span></span>  
  
-   <span data-ttu-id="7b6a7-112">`//`es una abreviación de `/descendant-or-self::node()/`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-112">`//` is short for `/descendant-or-self::node()/`.</span></span>  
  
-   <span data-ttu-id="7b6a7-113">`.`es una abreviación de `self::node()`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-113">`.` is short for `self::node()`.</span></span>  
  
-   <span data-ttu-id="7b6a7-114">`..`es una abreviación de `parent::node()`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-114">`..` is short for `parent::node()`.</span></span>  
  
 <span data-ttu-id="7b6a7-115">Las expresiones XPath canónicas son expresiones simples como `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-115">Canonical XPath expressions are simple expressions such as `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span></span>  
  
 <span data-ttu-id="7b6a7-116">Esto contrasta con la forma no canónica de XPath.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-116">This can be contrasted with the non-canonical form of XPath.</span></span> <span data-ttu-id="7b6a7-117">Este formulario es también se denomina el "forma general" o "XPath arbitrario" y se distingue mediante expresiones arbitrariamente complejas y pueden combinar varios ejes: `//element-name//*[local-name()='element-name' and position()=2]`.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-117">This form is also known as the "general form" or "arbitrary XPath" and is distinguished by expressions that are arbitrarily complex and may combine multiple axes: `//element-name//*[local-name()='element-name' and position()=2]`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b6a7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b6a7-118">Example</span></span>  
 <span data-ttu-id="7b6a7-119">Observe el programa siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-119">Consider the following program:</span></span>  
  
```  
using System;  
using System.IO;  
using System.Xml.Serialization;  
using Microsoft.XLANGs.BaseTypes;  
  
namespace ComplexNetXPath  
{  
    public class Animal  
    {  
        [Property( typeof(BTS.RetryCount) )]  
        public int NumberOfLegs;  
    }   
    public class Snake : Animal  
    {  
        public Snake()  
        {  
            NumberOfLegs = 0;  
        }  
    }   
    public class Dog : Animal  
    {  
        public Dog()  
        {  
            NumberOfLegs = 4;  
        }  
    }   
    public class Zoo  
    {  
        //  
        // Dogs and snakes are the possible animals of  
        // the week.  
        //  
        [XmlElement(typeof(Snake))]  
        [XmlElement(typeof(Dog))]  
        public Animal AnimalOfTheWeek;  
    }  
    class Class1  
    {  
        static void Main(string[] args)  
        {  
            XmlSerializer ser = new XmlSerializer(typeof(Zoo));  
            Stream s = Console.OpenStandardOutput();  
            Zoo z = new Zoo();  
            z.AnimalOfTheWeek = new Dog();  
            ser.Serialize( s, z );  
            s.Flush();  
            Console.WriteLine("------------------");  
            z.AnimalOfTheWeek = new Snake();  
            ser.Serialize( s, z );  
            s.Flush();  
        }  
    }  
}   
```  
  
 <span data-ttu-id="7b6a7-120">El tipo Zoo contiene un campo Animal que puede ser Snake o Dog.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-120">The Zoo type contains an Animal field that may be either a Snake or a Dog.</span></span> <span data-ttu-id="7b6a7-121">La instancia Animal tiene un campo NumberOfLegs que se anota con PropertyAttribute, con lo que la propiedad BTS.RetryCount se asigna a este campo.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-121">The Animal instance has a NumberOfLegs field that is annotated with the PropertyAttribute which assigns the BTS.RetryCount property to this field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b6a7-122">Una aplicación real definiría sus propias propiedades.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-122">A real application would define its own properties.</span></span>  
  
 <span data-ttu-id="7b6a7-123">Cuando el animal de la semana es Dog, la instancia de Zoo serializada tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-123">When the animal of the week is a dog, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 <span data-ttu-id="7b6a7-124">Cuando el animal de la semana es Snake, la instancia de Zoo serializada tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-124">When the animal of the week is a snake, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 <span data-ttu-id="7b6a7-125">Al considerar el esquema XML equivalente a la clase de .Net Zoo, la expresión de XPath para seleccionar la propiedad RetryCount permitiría la aparición de un paso Snake o Dog en la ruta de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-125">Considering the Xml schema equivalent to the .Net Zoo class, the XPath expression for selecting the RetryCount property would allow for either a Snake or a Dog step to appear on the path to the property:</span></span>  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 <span data-ttu-id="7b6a7-126">Los componentes de canalización XML no pueden controlar esta expresión de XPath no canónico.</span><span class="sxs-lookup"><span data-stu-id="7b6a7-126">The XML pipeline components cannot handle this non-canonical XPath expression.</span></span> <span data-ttu-id="7b6a7-127">Para evitar esta situación, los atributos de serialización XML de varias opciones de tipo test no deberían utilizarse junto con las canalizaciones XML; además, se debería tener cuidado al utilizar los siguientes atributos de serialización XML:</span><span class="sxs-lookup"><span data-stu-id="7b6a7-127">To avoid this situation, multiple-choice Xml serialization attributes should not be used in conjunction with the XML pipelines and care should be taken when using the following xml serialization attributes:</span></span>  
  
-   <span data-ttu-id="7b6a7-128">XmlElementAttribute</span><span class="sxs-lookup"><span data-stu-id="7b6a7-128">XmlElementAttribute</span></span>  
  
-   <span data-ttu-id="7b6a7-129">XmlAttributeAttribute</span><span class="sxs-lookup"><span data-stu-id="7b6a7-129">XmlAttributeAttribute</span></span>  
  
-   <span data-ttu-id="7b6a7-130">XmlArrayItemAttribute</span><span class="sxs-lookup"><span data-stu-id="7b6a7-130">XmlArrayItemAttribute</span></span>
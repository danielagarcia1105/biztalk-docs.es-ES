---
title: Cómo agregar Namespace ejemplo funciona | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c76a90a9-5898-43b3-98af-ff546dd97153
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212364030353001cae0589d4d7562641db4b77e6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22294388"
---
# <a name="how-the-add-namespace-sample-works"></a><span data-ttu-id="85bf0-102">Cómo agregar Namespace ejemplo funciona</span><span class="sxs-lookup"><span data-stu-id="85bf0-102">How the Add Namespace Sample Works</span></span>
<span data-ttu-id="85bf0-103">El primer, segundo y cuarta pruebas utilizan el **agregar Namespace** componente ubicado en la canalización de NamespaceSampleReceivePipeline.</span><span class="sxs-lookup"><span data-stu-id="85bf0-103">The first, second, and fourth tests use the **Add Namespace** component located in the NamespaceSampleReceivePipeline pipeline.</span></span> <span data-ttu-id="85bf0-104">Toma como entrada un documento con ningún espacio de nombres en el nodo raíz, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="85bf0-104">It takes as input a document with no namespace on the root node, such as the following:</span></span>  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  
  
 <span data-ttu-id="85bf0-105">La tabla siguiente muestran los valores de propiedad establecidos para el **agregar Namespace** componente.</span><span class="sxs-lookup"><span data-stu-id="85bf0-105">The following table shows the property values set for the **Add Namespace** component.</span></span>  
  
|<span data-ttu-id="85bf0-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="85bf0-106">Property</span></span>|<span data-ttu-id="85bf0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="85bf0-107">Type</span></span>|<span data-ttu-id="85bf0-108">Value</span><span class="sxs-lookup"><span data-stu-id="85bf0-108">Value</span></span>|  
|--------------|----------|-----------|  
|<span data-ttu-id="85bf0-109">ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="85bf0-109">ExtractionNodeXPath</span></span>|<span data-ttu-id="85bf0-110">Estático</span><span class="sxs-lookup"><span data-stu-id="85bf0-110">Static</span></span>|<span data-ttu-id="85bf0-111">(vacío)</span><span class="sxs-lookup"><span data-stu-id="85bf0-111">(empty)</span></span>|  
|<span data-ttu-id="85bf0-112">NamespaceBase</span><span class="sxs-lookup"><span data-stu-id="85bf0-112">NamespaceBase</span></span>|<span data-ttu-id="85bf0-113">Estático</span><span class="sxs-lookup"><span data-stu-id="85bf0-113">Static</span></span>|http://schemas.microsoft.biztalk.esb.test.com/test|  
|<span data-ttu-id="85bf0-114">NamespacePrefix</span><span class="sxs-lookup"><span data-stu-id="85bf0-114">NamespacePrefix</span></span>|<span data-ttu-id="85bf0-115">Estático</span><span class="sxs-lookup"><span data-stu-id="85bf0-115">Static</span></span>|<span data-ttu-id="85bf0-116">esbTest</span><span class="sxs-lookup"><span data-stu-id="85bf0-116">esbTest</span></span>|  
|<span data-ttu-id="85bf0-117">Separador</span><span class="sxs-lookup"><span data-stu-id="85bf0-117">Separator</span></span>|<span data-ttu-id="85bf0-118">Estático</span><span class="sxs-lookup"><span data-stu-id="85bf0-118">Static</span></span>|/|  
|<span data-ttu-id="85bf0-119">XPaths</span><span class="sxs-lookup"><span data-stu-id="85bf0-119">XPaths</span></span>|<span data-ttu-id="85bf0-120">Dinámica</span><span class="sxs-lookup"><span data-stu-id="85bf0-120">Dynamic</span></span>|<span data-ttu-id="85bf0-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span><span class="sxs-lookup"><span data-stu-id="85bf0-121">/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate</span></span>|  
  
 <span data-ttu-id="85bf0-122">Los valores de propiedad se muestra en la tabla provocar que el componente buscar el documento XML mediante la ejecución de las dos consultas XPath /CanonicalOrder/@OrderID y /CanonicalOrder/@OrderDate (las dos consultas especificadas para la **XPaths** propiedad, separados por una "canalización" carácter).</span><span class="sxs-lookup"><span data-stu-id="85bf0-122">The property settings shown in the table cause the component to search the XML document by executing the two XPath queries /CanonicalOrder/@OrderID and /CanonicalOrder/@OrderDate (the two queries specified for the **XPaths** property, separated by a "pipe" character).</span></span> <span data-ttu-id="85bf0-123">Estas consultas devuelven los valores de la **OrderID** y **OrderDate** atributos del nodo raíz del documento; en este ejemplo, los dos valores son "OrderID_0" y "OrderDate_1".</span><span class="sxs-lookup"><span data-stu-id="85bf0-123">These queries return the values of the **OrderID** and **OrderDate** attributes of the root node of the document; in this example, the two values are "OrderID_0" and "OrderDate_1".</span></span>  
  
 <span data-ttu-id="85bf0-124">A continuación, el componente utiliza estos valores y los valores de las demás propiedades, para crear el nuevo espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="85bf0-124">The component then uses these values, and the values of the other properties, to construct the new root namespace.</span></span> <span data-ttu-id="85bf0-125">Combina el **NamespaceBase**, el **NamespacePrefix**, **separador**y los valores de las dos consultas de XPath en el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="85bf0-125">It combines the **NamespaceBase**, the **NamespacePrefix**, the **Separator**, and the values from the two XPath queries in the following format:</span></span>  
  
```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  
  
 <span data-ttu-id="85bf0-126">Esto genera el nuevo espacio de nombres, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="85bf0-126">This produces the new namespace, as shown here:</span></span>  
  
```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  
  
 <span data-ttu-id="85bf0-127">Por lo tanto, el documento actualizado después del procesamiento por la **NamespaceSampleReceivePipeline** canalización es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="85bf0-127">Therefore, the updated document after processing by the **NamespaceSampleReceivePipeline** pipeline is the following:</span></span>  
  
```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  
  
## <a name="using-the-extractionnodexpath-property"></a><span data-ttu-id="85bf0-128">Mediante la propiedad ExtractionNodeXPath</span><span class="sxs-lookup"><span data-stu-id="85bf0-128">Using the ExtractionNodeXPath Property</span></span>  
 <span data-ttu-id="85bf0-129">De forma predeterminada, el **agregar Namespace** componente usa el elemento raíz del documento XML dentro del mensaje cuando se agrega información de espacio de nombres y prefijo.</span><span class="sxs-lookup"><span data-stu-id="85bf0-129">By default, the **Add Namespace** component uses the root element of the XML document within the message when adding namespace and prefix information.</span></span> <span data-ttu-id="85bf0-130">Si desea utilizar solo un subconjunto del documento XML como el cuerpo del mensaje (resulta útil en ciertos escenarios de sobres o cuando solo una parte de un documento entrante tiene relevancia), puede establecer la **ExtractionNodeXPath** propiedad para forzar la  **Agregar Namespace** componente para buscar el elemento especificado para su uso como el mensaje resultante.</span><span class="sxs-lookup"><span data-stu-id="85bf0-130">If you want to use only a subset of the XML document as the message body (useful in certain envelope scenarios or when only a portion of an inbound document has relevance), you can set the **ExtractionNodeXPath** property to force the **Add Namespace** component to seek the specified element for use as the resultant message.</span></span> <span data-ttu-id="85bf0-131">Por ejemplo, si sabe que un mensaje recibido de CanonicalOrder tendrá un único **OrderDetails** elemento que es relevante para los consumidores de este mensaje incluidos en él, puede establecer la **ExtractionNodeXPath** propiedad para especificar la ruta de acceso a la **OrderDetails** elemento.</span><span class="sxs-lookup"><span data-stu-id="85bf0-131">For example, if you know that a received CanonicalOrder message will have only one **OrderDetails** element that is relevant for consumers of this message contained within it, you can set the **ExtractionNodeXPath** property to specify the path to the **OrderDetails** element.</span></span> <span data-ttu-id="85bf0-132">Puede ver un ejemplo de este proceso en la extracción agregar a través a prueba de acceso directo que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="85bf0-132">You can see an example of this process in the Add Via Extraction to Pass-through test described earlier.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85bf0-133">El **ExtractionNodeXPath** propiedad debe ser una expresión XPath que devuelve un único elemento.</span><span class="sxs-lookup"><span data-stu-id="85bf0-133">The **ExtractionNodeXPath** property must be an XPath that returns only one element.</span></span> <span data-ttu-id="85bf0-134">El componente, producirá una excepción si el resultado no es un elemento o si la consulta XPath devuelve más de un elemento.</span><span class="sxs-lookup"><span data-stu-id="85bf0-134">The component will raise an exception if the result is not an element or if the XPath query returns more than one element.</span></span>
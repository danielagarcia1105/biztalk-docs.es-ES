---
title: Problemas de localización del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d200ce9-1a60-455b-88b0-6ec86092a786
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8862318547f2a7b8b4fa5dc7291e1673f1b9ba29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229868"
---
# <a name="adapter-localization-issues"></a><span data-ttu-id="ba12c-102">Problemas de localización del adaptador</span><span class="sxs-lookup"><span data-stu-id="ba12c-102">Adapter Localization Issues</span></span>
<span data-ttu-id="ba12c-103">En los temas siguientes se tratan problemas de localización que puede encontrar cuando desarrolle adaptadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="ba12c-103">The following topics cover localization issues that you may encounter when developing custom adapters.</span></span>  
  
## <a name="xsd-issues"></a><span data-ttu-id="ba12c-104">Problemas de XSD</span><span class="sxs-lookup"><span data-stu-id="ba12c-104">XSD Issues</span></span>  
 <span data-ttu-id="ba12c-105">Al usar el marco de trabajo de adaptadores, los programadores del adaptador pueden implementar páginas de propiedades del adaptador con esquemas de Lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="ba12c-105">By using the Adapter Framework, adapter developers can implement adapter property pages with XML Schema Definition (XSD) schemas.</span></span>  
  
 <span data-ttu-id="ba12c-106">Si el adaptador no tiene ningún requisito de globalización o localización, puede codificar la cadena de esquema XSD en el **IDynamicAdapterConfig: Getconfigschema** función.</span><span class="sxs-lookup"><span data-stu-id="ba12c-106">If your adapter has no globalization or localization requirements, then you can hard code the XSD schema string inside the **IDynamicAdapterConfig:GetConfigSchema** function.</span></span>  
  
 <span data-ttu-id="ba12c-107">En cambio, si el adaptador tiene requisitos de globalización o localización, puede implementar el esquema XSD de una de las dos maneras posibles.</span><span class="sxs-lookup"><span data-stu-id="ba12c-107">If your adapter has globalization or localization requirements, you can implement the XSD schema in one of two ways.</span></span>  
  
-   <span data-ttu-id="ba12c-108">Usar archivos XSD diferentes fuera del binario en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ba12c-108">Use separate XSD files outside the design-time binary.</span></span> <span data-ttu-id="ba12c-109">Convertir el texto completo del esquema en un recurso de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="ba12c-109">Make the whole text of the schema a manifest resource.</span></span>  
  
-   <span data-ttu-id="ba12c-110">Reemplazar dinámicamente los nombres de propiedades y la descripción del recurso:</span><span class="sxs-lookup"><span data-stu-id="ba12c-110">Dynamically replace the Property Names and Description from the resource:</span></span>  
  
    -   <span data-ttu-id="ba12c-111">Agregar un _locID a cada elemento que vaya a localizar.</span><span class="sxs-lookup"><span data-stu-id="ba12c-111">Add a _locID to each element that you want to localize.</span></span>  
  
    -   <span data-ttu-id="ba12c-112">Usar una Xpath para retirar todos los nodos del esquema que tengan un atributo _locID.</span><span class="sxs-lookup"><span data-stu-id="ba12c-112">Use an xpath to pull back all the nodes in the schema that have a _locID attribute.</span></span>  
  
    -   <span data-ttu-id="ba12c-113">Buscar los recursos de una cadena indizada por el valor del _locID.</span><span class="sxs-lookup"><span data-stu-id="ba12c-113">Look up the resources for a string indexed by the value of the _locID.</span></span>  
  
    -   <span data-ttu-id="ba12c-114">Reemplazar el texto del nodo con el resultado.</span><span class="sxs-lookup"><span data-stu-id="ba12c-114">Replace the node text with the result.</span></span>  
  
 <span data-ttu-id="ba12c-115">A continuación, se muestra un código de ejemplo de la segunda opción:</span><span class="sxs-lookup"><span data-stu-id="ba12c-115">The following is sample code for the second option:</span></span>  
  
```  
string mySchema = GetSchemaFromResource(“mySchema”);  
string myLocalizedSchema = LocalizeSchemaDOM (mySchema, resourceManager);  
//  where…  
protected string GetSchemaFromResource (string name)  
{  
Assembly assem = this.GetType().Assembly;  
Stream stream = assem.GetManifestResourceStream(name);  
StreamReader reader = new StreamReader(stream);  
string schema = reader.ReadToEnd();  
return schema;  
}  
  
protected XmlDocument LocalizeSchemaDOM (string schema, ResourceManager resourceManager)  
{  
XmlDocument document = new XmlDocument();  
document.LoadXml(schema);  
XmlNodeList nodes = document.SelectNodes  
("/descendant::*[@_locID]");  
foreach (XmlNode node in nodes)  
{  
string locID = node.Attributes["_locID"].Value;  
node.InnerText = resourceManager.GetString(locID);  
}  
return document;  
}  
```
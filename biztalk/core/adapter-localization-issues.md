---
title: Problemas de localización de adaptador | Microsoft Docs
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
ms.openlocfilehash: c829ce496c124f3333c353f481eb3958e29d5c77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996341"
---
# <a name="adapter-localization-issues"></a>Problemas de localización del adaptador
En los temas siguientes se tratan problemas de localización que puede encontrar cuando desarrolle adaptadores personalizados.  
  
## <a name="xsd-issues"></a>Problemas de XSD  
 Al usar el marco de trabajo de adaptadores, los programadores del adaptador pueden implementar páginas de propiedades del adaptador con esquemas de Lenguaje de definición de esquemas XML (XSD).  
  
 Si el adaptador no tiene ningún requisito de globalización o localización, puede codificar la cadena de esquema XSD dentro de la **IDynamicAdapterConfig: Getconfigschema** función.  
  
 En cambio, si el adaptador tiene requisitos de globalización o localización, puede implementar el esquema XSD de una de las dos maneras posibles.  
  
- Usar archivos XSD diferentes fuera del binario en tiempo de diseño. Convertir el texto completo del esquema en un recurso de manifiesto.  
  
- Reemplazar dinámicamente los nombres de propiedades y la descripción del recurso:  
  
  -   Agregar un _locID a cada elemento que vaya a localizar.  
  
  -   Usar una Xpath para retirar todos los nodos del esquema que tengan un atributo _locID.  
  
  -   Buscar los recursos de una cadena indizada por el valor del _locID.  
  
  -   Reemplazar el texto del nodo con el resultado.  
  
  A continuación, se muestra un código de ejemplo de la segunda opción:  
  
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
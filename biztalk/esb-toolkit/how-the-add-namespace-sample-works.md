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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212364030353001cae0589d4d7562641db4b77e6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-the-add-namespace-sample-works"></a>Cómo agregar Namespace ejemplo funciona
El primer, segundo y cuarta pruebas utilizan el **agregar Namespace** componente ubicado en la canalización de NamespaceSampleReceivePipeline. Toma como entrada un documento con ningún espacio de nombres en el nodo raíz, como la siguiente:  
  
```  
<CanonicalOrder OrderID="OrderID_0" OrderDate="OrderDate_1" Status="Status_2">  
```  
  
 La tabla siguiente muestran los valores de propiedad establecidos para el **agregar Namespace** componente.  
  
|Propiedad|Tipo|Value|  
|--------------|----------|-----------|  
|ExtractionNodeXPath|Estático|(vacío)|  
|NamespaceBase|Estático|http://schemas.microsoft.biztalk.esb.test.com/test|  
|NamespacePrefix|Estático|esbTest|  
|Separador|Estático|/|  
|XPaths|Dinámica|/CanonicalOrder/@OrderID&#124;/CanonicalOrder/@OrderDate|  
  
 Los valores de propiedad se muestra en la tabla provocar que el componente buscar el documento XML mediante la ejecución de las dos consultas XPath /CanonicalOrder/@OrderID y /CanonicalOrder/@OrderDate (las dos consultas especificadas para la **XPaths** propiedad, separados por una "canalización" carácter). Estas consultas devuelven los valores de la **OrderID** y **OrderDate** atributos del nodo raíz del documento; en este ejemplo, los dos valores son "OrderID_0" y "OrderDate_1".  
  
 A continuación, el componente utiliza estos valores y los valores de las demás propiedades, para crear el nuevo espacio de nombres raíz. Combina el **NamespaceBase**, el **NamespacePrefix**, **separador**y los valores de las dos consultas de XPath en el siguiente formato:  
  
```  
xmlns:{NamespacePrefix}="{NamespaceBase}{Separator}{XPaths[1]}{Seperator}  
                         {XPaths[2]}{Separator}...{XPaths[n]}"  
```  
  
 Esto genera el nuevo espacio de nombres, como se muestra aquí:  
  
```  
xmlns:esbTest="http://schemas.microsoft.biztalk.esb.test.com/test  
               /OrderID_0/OrderDate_1"  
```  
  
 Por lo tanto, el documento actualizado después del procesamiento por la **NamespaceSampleReceivePipeline** canalización es el siguiente:  
  
```  
<esbTest:CanonicalOrder xmlns:esbTest=  
    "http://schemas.microsoft.biztalk.esb.test.com/test/OrderID_0  
    /OrderDate_1" OrderID="OrderID_0" OrderDate="OrderDate_1"   
    Status="Status_2">  
```  
  
## <a name="using-the-extractionnodexpath-property"></a>Mediante la propiedad ExtractionNodeXPath  
 De forma predeterminada, el **agregar Namespace** componente usa el elemento raíz del documento XML dentro del mensaje cuando se agrega información de espacio de nombres y prefijo. Si desea utilizar solo un subconjunto del documento XML como el cuerpo del mensaje (resulta útil en ciertos escenarios de sobres o cuando solo una parte de un documento entrante tiene relevancia), puede establecer la **ExtractionNodeXPath** propiedad para forzar la  **Agregar Namespace** componente para buscar el elemento especificado para su uso como el mensaje resultante. Por ejemplo, si sabe que un mensaje recibido de CanonicalOrder tendrá un único **OrderDetails** elemento que es relevante para los consumidores de este mensaje incluidos en él, puede establecer la **ExtractionNodeXPath** propiedad para especificar la ruta de acceso a la **OrderDetails** elemento. Puede ver un ejemplo de este proceso en la extracción agregar a través a prueba de acceso directo que se ha descrito anteriormente.  
  
> [!NOTE]
>  El **ExtractionNodeXPath** propiedad debe ser una expresión XPath que devuelve un único elemento. El componente, producirá una excepción si el resultado no es un elemento o si la consulta XPath devuelve más de un elemento.
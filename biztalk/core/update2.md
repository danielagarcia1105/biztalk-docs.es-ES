---
title: "Actualización2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 770c9ebb-df3a-428f-be18-b36535352f8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4376cae94e91f462974c626a57170b80b0117ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="update"></a>Update
El elemento `Update` se usa para extraer datos de un evento y lo importa en la actividad de BAM relacionada.  
  
## <a name="format"></a>Formato  
 Para usar el `Update` elemento, debe proporcionar un nombre de columna y el tipo y un **expresión** elemento que contiene uno o más **operación** elementos que se evalúan como un valor de cadena único.  
  
```  
<ic:Update DataItemName="Name" Type="Type">  
  <ic:Expression>  
    <!-- one or more Operation elements -->  
  </ic:Expression>  
</ic:Update>  
```  
  
### <a name="attributes"></a>Atributos  
  
|Nombre del atributo|Description|  
|--------------------|-----------------|  
|ColumnName|Nombre de punto de control de actividad de BAM. Éste es el punto de control que se actualizará con los datos extraídos.|  
|Tipo|El tipo de datos de BAM del punto de control debe ser uno de los siguientes:<br /><br /> -NVARCHAR<br />-FECHA Y HORA<br />-INT<br />-FLOAT|  
  
## <a name="remarks"></a>Comentarios  
 Las siguientes operaciones no se admiten en la expresión `Update`:  
  
-   And  
  
-   Es igual a  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la **GetContextProperty** operación WF se utiliza para recuperar la **EventTime** propiedad. Este valor se almacenará como un **DATETIME** tipo para el elemento de datos "StartOrderProcessing" para la actividad de BAM.  
  
```  
<ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)
---
title: Referencia | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b916c55a-c84c-4008-8927-f8e584c36fe9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3e32145e2340a4d86a6893db3e9209b79c2b5e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reference"></a>Referencia
El **referencia** elemento se puede usar para agregar una o varias relaciones a una actividad de BAM. Resulta útil cuando se desea adjuntar un puntero como una clave principal, un Id. o una URL a un mensaje relacionado. Por ejemplo, podría almacenar una referencia a un lote de envío en una actividad de pedido.  
  
## <a name="format"></a>Formato  
 El `Reference` elemento admite tanto la **datos** y **LongData** los elementos secundarios que contienen una expresión que especifica los datos que se va a asociar a la actividad de BAM. Puede usar cualquier combinación de **datos** y **LongData** para satisfacer los requisitos de seguimiento.  
  
### <a name="attributes"></a>Atributos  
  
|Nombre del atributo|Description|  
|--------------------|-----------------|  
|Nombre|Nombre de la relación que se adjuntará a la actividad de BAM.|  
|Tipo|Cadena arbitraria que especifica el tipo de relación que se adjuntará a la actividad de BAM. Se admiten las cadenas arbitrarias y los siguientes tipos de BAM predefinidos:<br /><br /> -BizTalkService<br />-MessageID<br />-Activity<br />-DocumentUrl<br />-InstanceID<br /><br /> Para obtener más información sobre tipos de referencia BAM predefinidos, vea [propiedades de la referencia](http://go.microsoft.com/fwlink/?LinkId=119601).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Estado de ejecución|Description|  
|----------------------|-----------------|  
|data|Especifica cómo extraer los datos de la cadena hasta 128 caracteres que se adjuntará a la actividad de BAM.|  
|LongData|Especifica cómo extraer los datos de cadenas largas arbitrariamente que se adjuntarán a la actividad de BAM.|  
  
> [!NOTE]
>  A `Reference` elemento puede combinar uno o varios **datos** y **LongData** los elementos secundarios según sea necesario.  
  
## <a name="remarks"></a>Comentarios  
 En expresiones de Reference, no se permiten las operaciones comunes siguientes:  
  
-   And  
  
-   Es igual a  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se crea una referencia con el nombre "Related Document" de tipo "DocumentUrl" por medio de `GetUserData` para un flujo de trabajo. Puesto que se espera que los datos del usuario sean inferiores a 1024 caracteres de longitud, el elemento `Data` se usa para contener el elemento `Expression`.  
  
```  
<ic:Reference Name="Related Document" Type="DocumentUrl">  
  <ic:Data>  
    <ic:Expression>  
      <wf:Operation Name="GetUserData" />  
    </ic:Expression>  
  </ic:Data>  
</ic:Reference>  
```  
  
 El **referencia** elemento admite una combinación de `Data` y `LongData` elementos. En el ejemplo siguiente, los campos del nombre del país y de notas de un pedido se recuperan de un Servicio WCF y se escriben en la relación "Long and Short Data" como tipo "MyType". Puesto que el campo de nota admite más de 1024 caracteres, la expresión aparece en un elemento `LongData`.  
  
```  
<ic:Reference Name="Long and Short Data" Type="MyType">  
  <ic:Data>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Country: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Country</wcf:Argument>  
      </wcf:Operation>  
       <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:Data>  
  <ic:LongData>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>Note: </ic:Argument>  
      </ic:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body//po:Note</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name="Concatenate" />  
    </ic:Expression>  
  </ic:LongData>  
</ic:Reference>  
```  
  
## <a name="see-also"></a>Vea también  
 [Elemento OnEvent del interceptor](../core/interceptor-onevent-element.md)   
 [Método EventStream.AddRelatedActivity](http://go.microsoft.com/fwlink/?LinkId=119602)
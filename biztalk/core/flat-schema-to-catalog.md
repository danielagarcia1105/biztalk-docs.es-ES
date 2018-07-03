---
title: Planos de esquema a catálogo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0e37afa-2329-4691-9fa1-82b8c7bcd59a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1dc8093d477773d5efbab46670bac7e9c839d8d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999045"
---
# <a name="flat-schema-to-catalog"></a>De esquema sin formato a catálogo

## <a name="overview"></a>Información general
Puede usar el **bucle** functoid para convertir un esquema sin formato en un esquema jerárquico asignando un único registro a múltiples registros. Ésta es una operación común para convertir esquemas sin formato en catálogos de Microsoft Commerce Server.  
  
 En el siguiente código se muestra una parte de un catálogo que enumera variantes de producto, y cada variante como su propio registro.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.FlatCatalog">  
    <ProductVariant ListPrice="99.99" ID="45-01" Material="Leather" Color="Black" />  
    <ProductVariant ListPrice="69.99" ID="45-02" Material="Vinyl" Color="Brown" />  
</ns0:Root>  
```  
  
 Expandir esta parte del catálogo convertiría algunos o todos los **ProductVariant** atributos en los registros.  
  
```  
<ns0:Root xmlns:ns0="http://ValueMappingFlattening.Catalog">  
    <ProductVariant ListPrice="99.99" ID="45-01">  
        <Feature Name="Material" Value="Leather"/>  
        <Feature Name="Color" Value="Black"/>  
    </ProductVariant>  
    <ProductVariant ListPrice="69.99" ID="45-02">  
        <Feature Name="Material" Value="Vinyl"/>  
        <Feature Name="Color" Value="Brown"/>  
    </ProductVariant>  
</ns0:Root>  
```  
  
 En la ilustración siguiente se muestra una asignación que realiza esta conversión.  
  
 ![Mapa que muestra el uso del functoid de bucle. ] (../core/media/loopingflattenfunctoid.gif "loopingflattenfunctoid")  
Functoid de bucle, asignación de esquema sin formato  

## <a name="set-the-schema"></a>Establecer el esquema  
 Para que este tipo de asignación funcione correctamente, debe hacer lo siguiente:  
  
- Para cada vínculo que conecte con el **nombre** campo del esquema de destino, establezca propiedades de vínculo para copiar el nombre de esquema de origen. Para obtener más información, consulte [vínculos de configurar](../core/configuring-links.md). Consulte también **propiedades de vínculo** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
- Para cada vínculo que conecte con el **valor** campo del esquema de destino, establezca el esquema de origen de las propiedades de vínculo para copiar el valor (predeterminado).  
  
- Para el vínculo que conecta el **bucle** functoid con el registro denominado **característica** en el esquema de destino, establezca el esquema de destino propiedades de vínculo para que coincida con los vínculos de arriba a abajo.  
  
  Para el inverso de esta asignación, convertir un esquema de catálogo en un esquema sin formato, vea [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids de bucle a un mapa](../core/how-to-add-looping-functoids-to-a-map.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md)
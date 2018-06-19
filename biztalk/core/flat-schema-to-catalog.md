---
title: Planos esquema al catálogo | Documentos de Microsoft
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
ms.openlocfilehash: 0f3a45ad66ca10ab829a4cc7279891487124c3cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246260"
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
  
 Expandir esta parte del catálogo convertiría algunos o todos los **ProductVariant** atributos en registros.  
  
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
  
-   Para cada vínculo que conecte con el **nombre** campo del esquema de destino, establezca propiedades de vínculo para copiar el nombre de esquema de origen. Para obtener más información, consulte [configurar vínculos](../core/configuring-links.md). Consulte también **propiedades de vínculo de** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
-   Para cada vínculo que conecte con el **valor** campo del esquema de destino, establezca el esquema de origen propiedades de vínculo para copiar el valor (predeterminado).  
  
-   Para el vínculo al conectar el **bucle** functoid con el registro denominado **característica** en el esquema de destino, establezca el esquema de destino propiedades de vínculo debe coincidir vínculos de arriba a abajo.  
  
 Para el inverso de esta asignación, convertir un esquema de catálogo a un esquema sin formato, vea [Functoid de asignación de valores (sin formato)](../core/value-mapping-flattening-functoid.md).  
  
## <a name="see-also"></a>Vea también  
 [Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md)   
 [Functoid de bucle](../core/looping-functoid.md)   
 [Valor de asignación de Functoid (sin formato)](../core/value-mapping-flattening-functoid.md)
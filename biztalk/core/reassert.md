---
title: Volver a imponer | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reassert"></a>Reassert
Para *imponer* significa llamar a la **Assert** función en un objeto que ya está en el motor de la memoria de trabajo. Un comando reassert es equivalente a emitir un comando retract y, a continuación, un comando assert para el objeto.  
  
## <a name="net-objects"></a>Objetos .NET  
 En primer lugar, se retrae el objeto y se quita cualquier acción de la agenda para las reglas que usan el objeto (en un predicado o una acción). A continuación, el objeto se vuelve a imponer en la memoria de trabajo y se evalúa como cualquier objeto que se haya impuesto recientemente. Esto significa que se vuelve a evaluar cualquier regla que utilice el objeto en un predicado y que las acciones se agregan a la agenda según corresponda. Cualquier regla evaluada anteriormente a **true** y use sólo el objeto en sus acciones tendrán sus acciones agregarse de nuevo a la agenda.  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 Cuando una nivel superior **TypedXmlDocument** (**TXD**) se vuelve a imponer, el elemento secundario **TXD**s que se crean cuando el nivel superior **TXD** es inicialmente impone tenga distintos comportamientos según el estado del elemento secundario **TXD**s. En el caso de un elemento secundario nuevo nodo o un nodo secundario que está desfasado, lo que significa que se ha cambiado al menos uno de sus campos en la directiva mediante el uso de una acción de regla, una aserción, o volver a imponer acción se realiza en el nodo secundario. Cualquier nodo secundario existente no modificado se conservará en la memoria de trabajo. El siguiente ejemplo es un escenario simplificado que describe los comportamientos de los nodos secundarios cuando se vuelve a imponer el nodo primario.  
  
 Supongamos que hay tres **TXD**s actualmente en la memoria de trabajo: **P**, **C**1, **C**2, y **C**3. **P** es el nivel superior **TXD**, el nodo primario; cada niño para el nodo contiene un campo **x**.  
  
 **P**  
  
 **C**1 (**C**1. **x** = 1)  
  
 **C**2 (**C**2. **x** = 1)  
  
 **C**3 (**C**3. **x** = 1)  
  
 Además, supongamos que se han realizado las siguientes operaciones como resultado de la acción de una regla:  
  
-   El campo (**x**) valor **C**2 se actualiza.  
  
-   **C**3 se elimina mediante código de usuario.  
  
-   Un nodo secundario adicional, **d.**, se agrega a **P** mediante código de usuario.  
  
> [!NOTE]
>  El motor de reglas de negocios no marcará como modificados los nodos de los que no tenga conocimiento. Por ejemplo, agregar, eliminar o modificar un nodo mediante programación en una aplicación externa.  
  
 La nueva representación de los objetos en la memoria de trabajo es la siguiente:  
  
 **P**  
  
 **C**1 (**C**1. **x** = 1)  
  
 **C**2 (**C**2. **x** = *0*)  
  
 **D**  
  
 Ahora, vuelva a imponer **P**. Los puntos siguientes resumen los comportamientos de los nodos secundarios:  
  
-   Nodo **C**2 se vuelve a imponer, porque se ha modificado después de su campo que se está actualizando.  
  
-   Nodo **C**3 se retrae de la memoria de trabajo.  
  
-   Nodo **d.** se impone en la memoria de trabajo.  
  
-   Nodo **C**1 permanece sin cambios en la memoria de trabajo, porque no se actualizó antes de **P** se volviese a imponer.  
  
## <a name="typeddatatable"></a>TypedDataTable  
 Si **imponer** se emite en una **TypedDataRow**, esa fila se retira y, a continuación, se impone en la memoria de trabajo. Si **imponer** se emite en el **TypedDataTable**, todos los asociados **TypedDataRow**se retraen y, a continuación, se imponen.  
  
## <a name="dataconnection"></a>DataConnection  
 Todos los **TypedDataRow**s recuperados a través de la **DataConnection** se retiran. Todos los predicados que utilizan el **DataConnection** se vuelven a evaluar, provocando la **DataConnection** para realizar una nueva consulta para crear la correspondiente **TypedDataRow**s.  
  
## <a name="see-also"></a>Vea también  
 [Funciones de Control del motor](../core/engine-control-functions.md)
---
title: XPath | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="xpath"></a>XPath
Inserta el valor indicado por una instrucción XPath.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Instrucción XPath válida.  
  
## <a name="pushed-value"></a>Valor insertado  
 Valor de cadena del resultado encontrado mediante la ejecución de la instrucción XPath.  
  
## <a name="remarks"></a>Comentarios  
 Debe usar una instrucción XPath válida.  
  
 En el caso en el que haya varias coincidencias, se usará sólo la primera de éstas.  
  
## <a name="example"></a>Ejemplo  
 En la siguiente expresión de ejemplo se construye un valor de correlación mediante la concatenación de una constante "C_" con el Id. de pedido de compra del mensaje actual. El Id. de pedido de compra se recupera mediante el uso de la operación XPath.  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)
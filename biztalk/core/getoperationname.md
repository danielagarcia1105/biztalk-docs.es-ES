---
title: GetOperationName | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e22020add39840b0d2fe4c2fd88156321a18c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getoperationname"></a>GetOperationName (operación)
Inserta el nombre de la operación en curso en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el nombre de la operación actual.  
  
## <a name="remarks"></a>Comentarios  
 Cuando use GetOperationName, asegúrese de que compara el nombre de la operación cuando la aplicación la invoca. Por ejemplo, si usa el atributo de nombre en un contrato de servicio para asignar un nombre personalizado, el cliente tendrá su proxy predeterminado generado con el nombre personalizado para el método. Sin embargo, la aplicación del servidor utilizará los nombres reales de métodos para las operaciones correspondientes y no el que se especifique en el atributo de nombre.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, `GetOperationName` se usa para crear una expresión que filtra la operación denominada "AuthorizePayment".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)
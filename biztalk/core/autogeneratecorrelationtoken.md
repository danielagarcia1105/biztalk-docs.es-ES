---
title: AutoGenerateCorrelationToken | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e396fd0b2c6153a5252d336b9af9c22bf9421fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230260"
---
# <a name="autogeneratecorrelationtoken"></a>AutoGenerateCorrelationToken (operación)
Genera automáticamente un token de correlación y lo coloca en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el token de correlación.  
  
## <a name="remarks"></a>Comentarios  
 Esta operación se puede usar cuando no hay ningún token de correlación presente en el mensaje, pero se sigue queriendo correlacionar la información procedente de una solicitud y una respuesta. Puede emplearse para correlacionar una solicitud/respuesta concreta en el cliente o en el servicio.  
  
> [!NOTE]
>  Si se quieren correlacionar los datos recopilados por la solicitud y la respuesta para el cliente y el servicio (a continuación), habrá que usar un elemento o elementos de datos procedentes del mensaje.  
  
## <a name="example"></a>Ejemplo  
 La expresión de correlación del ejemplo siguiente se basa en `AutoGenerateCorrelationToken` para generar un token de correlación.  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de Windows Communication Foundation](../core/operations-in-windows-communication-foundation.md)
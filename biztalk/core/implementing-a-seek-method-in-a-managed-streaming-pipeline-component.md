---
title: Implementar un método Seek en un componente de canalización de transmisión por secuencias administrado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline interfaces, IStream interface
- pipeline components [custom], code samples
- IStream interface
- Seek method
ms.assetid: 2e546c41-822d-4e22-a8f6-8959072ef3d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5181957f691502dcc2b09a367c31de575097d1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256524"
---
# <a name="implementing-a-seek-method-in-a-managed-streaming-pipeline-component"></a>Implementar un método Seek en un componente de canalización administrado de transmisión por secuencias
Nativo **IStream** interfaz no proporciona un método para comprobar la posición de la secuencia actual, por lo que el motor de mensajería usa las siguientes **Seek** método.  
  
```  
pStream->Seek(0, STREAM_SEEK_CUR, &pNewPosition);  
```  
  
 Este método no mueve el puntero de la secuencia sino que consulta sobre la posición actual. Si implementa un componente de canalización que funciona con un flujo no permite búsquedas, puede usar el **Stream.Seek** método como en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
override public long Seek(long offset, SeekOrigin origin)  
{  
   long pos = -1;  
  
   switch(origin)  
   {  
      case SeekOrigin.Begin :  
         pos = offset;  
         break;  
      case SeekOrigin.Current :  
         pos = Position + offset;  
         break;  
      case SeekOrigin.End :  
         break;  
   }  
  
   // We generally disallow seeking of the stream  
   // However, in unmanaged code, many people use Seek(0,CURR) to retrieve    // the current position  
   // Special case (that is, if Seek does not change position, do not   
   // throw an exception)  
   if (pos==Position)  
   {  
      return pos;  
   }  
   else  
   {  
      throw new NotSupportedException("ForwardOnlyEventingReadStream does not support Seek()");  
   }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar componentes de canalización personalizado](../core/developing-custom-pipeline-components.md)
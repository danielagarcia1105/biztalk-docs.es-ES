---
title: "Detalles de implementación del adaptador OPS | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3172759541f46ec6c3c8c2b3e684086747036f37
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="ops-adapter-implementation-details"></a>Detalles de implementación de adaptadores de OPS
Puede que le resulte de utilidad conocer los siguientes aspectos del adaptador OPS al modificar el adaptador o configurarlo mediante programación.  
  
> [!NOTE]
>  El adaptador OPS se integra mediante el marco de trabajo de adaptadores. Para obtener información sobre la creación de adaptadores con el marco de trabajo, consulte [desarrollar adaptadores Custom](../core/developing-custom-adapters.md).  
  
## <a name="batch-processing"></a>Procesamiento por lotes  
 El adaptador realiza el procesamiento de los mensajes uno por uno, para llevarlo a cabo de forma independiente, y las reversiones se llevan a cabo en un sólo pedido cada vez. Pese a que el adaptador procese uno por uno los mensajes, lo hace mediante el procesamiento por lotes con un tamaño de lote de mensaje. Esto facilita la modificación del adaptador para controlar los mensajes de los lotes.  
  
## <a name="transaction-handling"></a>Control de transacciones  
 El adaptador utiliza los servicios de transacción proporcionados por Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions** instalaciones. El adaptador crea un nuevo **CommittableTransaction** y se utiliza con un **TransactionScope**. El adaptador llama el **inicializar** y **Execute** métodos dentro del contexto de esta transacción. Código del ensamblado llamado puede participar en la transacción mediante el uso de **Transaction.Current** método estático para obtener el contexto de transacción. El controlador de errores de ejemplo no emplea este servicio. Para obtener más información acerca de **System.Transactions**, vea "Namespace System.Transactions" en la versión de biblioteca de clases de .NET Framework.  
  
## <a name="handling-data-other-than-error-reports"></a>Controlar datos distintos de los informes de errores  
 En la solución, el adaptador controla los mensajes de informes de errores a partir de la nueva característica de informes de errores. Sin embargo, dado que la **Execute** método toma una matriz de bytes como su único argumento, no hay nada que limite de forma específica lo que puede pasarse a la **Execute** método.  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a>Uso del adaptador al crear puertos mediante programación  
 Puede especificar el adaptador cuando cree puertos a partir de código. La siguiente tabla recoge los nombres de las propiedades personalizadas, así como la forma en la que se corresponden con los nombres para mostrar.  
  
|Nombre de propiedad personalizada de envío|Nombre para mostrar|  
|-------------------------------|------------------|  
|**DotNetAssemblyStrongName**|**DotNetAssemblyStrongName**|  
|**DotNetClassName**|**DotNetClassName**|  
|**InitializationData**|**InitializationData**|  
|**Transportlocationuri se construye a**|No aplicable.|  
  
 Todas las propiedades son valores de cadena. El valor de la propiedad TransportLocationUri se construye a partir del nombre de ensamblado y del nombre de clase. El identificador URI tiene el valor OPS: / /\<DotNetAssemblyStrongName\>/\<DotNetClassName\> donde los marcadores de posición se reemplazan por los valores de la propiedad personalizada correspondiente.  
  
 Para obtener información sobre la creación de puertos desde el código, vea [cómo crear ubicaciones de recepción de MSMQ y puertos de envío desde el código](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).  
  
## <a name="see-also"></a>Vea también  
 [El adaptador de Ops](../core/the-ops-adapter.md)
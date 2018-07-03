---
title: Problemas comunes con los interceptores de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32145e2-1367-4576-9103-86c9182c11a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e6217a96bfbbe0a9dfddef6e8cec5a82cb93254
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004077"
---
# <a name="common-issues-with-the-bam-interceptors"></a>Problemas comunes de los interceptores de BAM
En este tema se explican los siguientes problemas comunes que pueden surgir al usar interceptores de BAM:  
  
-   Excepción de SQL relacionada con una transacción distribuida  
  
## <a name="you-receive-a-sql-exception-concerning-a-completed-distributed-transaction-or-a-transaction-descriptor"></a>Se recibe una excepción de SQL relacionada con una transacción distribuida completada o con un descriptor de la transacción  
 Al ejecutar el interceptor de Windows Communication Framework (WCF) de BAM, se puede ver alguna de las excepciones siguientes:  
  
- Se completó la transacción distribuida. Dé de alta esta sesión en una nueva transacción o en la transacción NULL.  
  
- No se permite el inicio de la nueva solicitud porque debe llegar con un descriptor válido de la transacción.  
  
  Algunas sugerencias para solucionar este problema son las siguientes:  
  
- Habilitar el seguimiento de BAM. Este seguimiento incluirá todos los mensajes relevantes, incluida la causa raíz del error. Para obtener más información acerca del seguimiento de BAM, consulte [cómo habilitar el seguimiento en BAM](../core/how-to-enable-tracing-in-bam.md).  
  
- Al ver la excepción del coordinador de transacciones distribuidas (DTC), intentar volver a ejecutar exactamente el mismo escenario sin transacciones.  
  
- Usar el Analizador de SQL Server y buscar errores en el seguimiento que originen la anulación de la transacción.  
  
## <a name="you-receive-an-error-similar-to-interceptor-configuration-polling-interval-0-must-be-at-least-5-seconds-when-using-the-wcf-interceptor"></a>Se recibe un error parecido a "El intervalo de sondeo '0' de la configuración del interceptor debe ser de '5' segundos" al usar el interceptor de WCF  
 Este error puede aparecer si no se proporciona de forma explícita un valor de intervalo de la configuración del interceptor en el archivo de configuración de la aplicación, o si se especifica un valor pero es inferior a 5 segundos, que es el valor mínimo necesario.  
  
 Para solucionar el problema, se debe especificar un valor válido para PollingIntervalSec como se muestra a continuación:  
  
```  
<BamEndpointBehaviorExtension ConnectionString="Initial Catalog=BamPrimaryImport;Data Source=MyMachine;Integrated Security=SSPI;" PollingIntervalSec="1500" />  
```  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de interceptores de BAM](../core/troubleshooting-bam-interceptors.md)
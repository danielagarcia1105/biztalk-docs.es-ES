---
title: Los interceptores de BAM en un entorno de alta disponibilidad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 555c8200-949f-4c7d-8041-5ba4b6cbaed5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79a697eb2a1a27ceeec1538ad8d46127413e7ed1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230740"
---
# <a name="bam-interceptors-in-a-high-availability-environment"></a>Interceptores de BAM en un entorno de alta disponibilidad
En este tema se describen los procesos de conmutación por error para el interceptor de WF de BAM y el interceptor de WCF de BAM en un entorno de alta disponibilidad durante una conmutación por error de SQL Server.  
  
## <a name="bam-wf-interceptor"></a>Interceptor de WF de BAM  
 Si se trabaja en un entorno de alta disponibilidad, el interceptor de WF de BAM volverá a intentar la recuperación del archivo de configuración del interceptor cuando haya un problema de conexión con SQL Server durante una conmutación por error de SQL Server. Sin embargo, el interceptor no realizará ningún reintento al escribir los datos en la base de datos de importación principal de BAM cuando una conmutación por error de SQL Server esté en proceso. Esto es porque el interceptor se basa en el comportamiento de la **WorkflowCommitBatchService** clase al escribir datos en la base de datos de importación principal de BAM.  
  
 En el ejemplo siguiente, **DefaultWorkflowCommitWorkBatchService** se agrega como un servicio de tiempo de ejecución con enableRetries = "true" para que el lote vuelve a intentar tal y como se muestra en un fragmento de código de un archivo App.config:  
  
```  
<add type="System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"  enableRetries="True"/>  
```  
  
 Sin embargo, si existen transacciones de ambiente cuando la **CommitWorkBatch** se llama al método, la instancia de flujo de trabajo se finaliza de forma inmediata cuando una conexión de SQL Server no está disponible.  
  
 Para obtener más información sobre el comportamiento de la **WorkflowCommitBatchService** de clases en un entorno de alta disponibilidad, vea la sección "Reliability and High Availability" en "Introducción a Hosting Windows Workflow Foundation" en [http://go.microsoft.com/fwlink/?LinkId=88068](http://go.microsoft.com/fwlink/?LinkId=88068).  
  
## <a name="bam-wcf-interceptor"></a>Interceptor de WCF de BAM  
 En un entorno de alta disponibilidad, el interceptor de WCF de BAM no vuelve a intentar la recuperación del archivo de configuración del interceptor cuando haya un problema de conexión con SQL Server durante una conmutación por error de SQL Server. Por tanto, debe personalizar el código WCF para compensar la conmutación por error o usar mensajería confiable para reenviar mensajes.  
  
## <a name="see-also"></a>Vea también  
 [Interceptor de WF de BAM](../core/bam-wf-interceptor.md)
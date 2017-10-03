---
title: "¿Qué son los interceptores de WF y de WCF de BAM? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a>¿Qué son los interceptores de WF y de WCF de BAM?
Supervisión de la actividad económica (BAM) es un conjunto de herramientas, API y servicios que le permiten administrar agregaciones, alertas y perfiles, y enviar eventos a los procesos automatizados de instrumentos para supervisar métricas empresariales pertinentes. En conjunto, proporcionan visibilidad en tiempo real en los procesos empresariales y le permiten conocer el estado de los procesos empresariales y resultados.  
  
 Los interceptores de BAM amplían esta misma funcionalidad a Windows Workflow Foundation (WF), Windows Communication Foundation (WCF) y a otros entornos en tiempos de ejecución. El interceptor de BAM le permite llevar el seguimiento de los procesos empresariales sin volver a compilar la solución WF o WCF: la integración se efectúa a través de un archivo de configuración.  
  
 Mediante el interceptor de WF o WCF de BAM en el proyecto, puede:  
  
-   Usar el portal BAM para ver información acerca de los procesos empresariales que se ejecutan en la aplicación WF o WCF.  
  
-   Usar la funcionalidad BAM sin agregar código adicional a la aplicación.  
  
-   Implementar la solución con las utilidades y herramientas de BizTalk Server que ya conoce.  
  
-   Aprovechar el entorno de BizTalk Server que ya existe para las aplicaciones WF y WCF nuevas y existentes.  
  
## <a name="interceptor-components"></a>Componentes del interceptor  
 En el núcleo de cada interceptor de BAM se encuentra Common Interceptor Foundation, un conjunto de componentes que proporciona las directrices para generar interceptores personalizados para entornos heterogéneos. Common Interceptor Foundation consta de los siguientes componentes compartidos:  
  
-   **bm.exe**, una versión mejorada de la utilidad de implementación de BAM extendida para modificar las configuraciones de interceptor incluidos add, remove, actualización y funcionalidad de la lista.  
  
-   **CommonInterceptorConfiguration.xsd**, el esquema XML de configuración de Common Interceptor Foundation. Como mínimo, la configuración de los interceptores debe validarse con este esquema.  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a>Interceptor de Windows Workflow Foundation (WF)  
 El interceptor de Windows Workflow Foundation interceptor permite agregar de forma transparente la funcionalidad de seguimiento de BAM a aplicaciones WF existentes y nuevas. Después de que se haya implementado la configuración del interceptor en la base de datos Importación principal de BAM y cada instancia de la aplicación WF se haya configurado para cargar el interceptor de WF de BAM, se escribirá los datos de flujo en BAM sin código adicional. El interceptor de WF proporciona la funcionalidad siguiente:  
  
-   Se conecta a aplicaciones WF existentes sin necesidad de cambios de código o recompilación.  
  
-   Habilita la detección en tiempo de ejecución y compatibilidad para archivos de configuración modificados. Si se detecta una nueva versión de un archivo de configuración de interceptor, las instancias de flujo de trabajo nuevas utilizarán la nueva configuración mientras que las instancias de flujo de trabajo antiguas se completarán mediante la configuración antigua.  
  
-   Admite transacciones. El interceptor de WF guarda los elementos de los que se ha realizado el seguimiento de forma transaccionalmente coherente con transacciones WF. Los elementos de los que se ha realizado el seguimiento sólo se guardan cuando la transacción WF y la transacción de interceptor se completa correctamente.  
  
    > [!NOTE]
    >  El interceptor de Windows Workflow no es compatible con SharedConnectionWorkflowCommitWorkBatchService que utiliza la misma conexión SQL para los servicios de persistencia y seguimiento.  
  
    > [!NOTE]
    >  En BizTalk Server, el interceptor de Windows Workflow Foundation (WF) no funcionará con el nuevo motor WF en .NET Framework 4. El interceptor de WF continuarán funcionando en .NET Framework 3.5 Service Pack 2.  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a>Interceptor de Windows Communication Foundation (WCF)  
 El interceptor de Windows Communication Foundation proporciona la funcionalidad de seguimiento de BAM a las aplicaciones WCF. Proporciona la siguiente funcionalidad:  
  
-   Se conecta a aplicaciones WCF existentes sin necesidad de cambios de código o recompilación.  
  
-   Realiza el seguimiento de mensajes contenidos en las llamadas del Servicio WCF.  
  
-   Realiza el seguimiento de la información procedente de mensajes en llamadas del Servicio WCF.  
  
-   Participa en transacciones procedentes del cliente o iniciadas internamente para llamadas de servicio con transacciones.
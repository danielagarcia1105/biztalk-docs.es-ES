---
title: Problemas conocidos con los interceptores WF y WCF de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2407809-1f71-41a9-b305-722a7f86af5b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42078eb2b1272072016ded9a117e88ddf4fda038
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-bam-wcf-and-wf-interceptors"></a>Problemas conocidos de los interceptores de WCF y WF de BAM
En esta sección se proporciona información acerca de problemas conocidos que puede encontrarse al utilizar los interceptores de BAM para Windows Workflow Foundation o Windows Communication Foundation.  
  
## <a name="intercepting-a-dynamically-generated-wcf-assembly-hosted-in-iis"></a>Interceptar un ensamblado de WCF generado de forma dinámica alojado en IIS  
 Cuando se usa IIS para alojar una aplicación de Windows Communication Foundation (WCF) integrada (por ejemplo, un archivo de servicio que especifica el origen del ensamblado), el ensamblado de WCF se generará de forma dinámica, se le asignará un nombre de archivo arbitrario y se colocará en la carpeta temporal asp.net. Debido a que el archivo de configuración del interceptor necesita información de manifiesto y debido a que en los archivos de configuración del interceptor no están disponibles los caracteres comodín ni otros métodos dinámicos para especificar el manifiesto, debe volver compilar el servicio y crear el archivo de configuración del interceptor o bien volver a implementar el archivo de configuración del interceptor una vez que ha implementado todas las páginas Web asp.net que contienen código de WCF integrado.  
  
## <a name="use-of-the-bam-interceptor-for-windows-workflow-foundation-is-not-supported-in-office-and-sharepoint-server"></a>Uso del interceptor de BAM para Windows Workflow Foundation no compatible con Office ni con Sharepoint Server  
 Tanto Office como Windows Sharepoint Server no leen en el archivo de configuración de la aplicación cuando inicializan el tiempo de ejecución de WF. Como resultado, el interceptor de BAM para WF se podría configurar para una aplicación aunque no se cargará en el tiempo de ejecución del flujo de trabajo cuando está alojado en estos entornos.  
  
## <a name="client-service-locks-when-intiating-a-distributed-transaction"></a>Bloqueo del servicio del cliente al iniciar una transacción distribuida  
 Si la operación del servicio no va a participar en la transacción que el cliente inicia y éste invoca el servicio desde el contexto de un ámbito de transacción, podría producirse un interbloqueo, en especial si hay datos que se recopilan desde el cliente antes de la solicitud de envío y desde el servicio por la solicitud de recepción para la misma actividad.  
  
 Para evitar esta situación, debe especificar que el cliente no participa en la transacción mediante la declaración "Enlist = false" en el atributo `ConnectionString` del cliente para la extensión de comportamiento de BAM en el archivo app.config del cliente, tal y como se muestra a continuación.  
  
```  
<behavior name="bamClientBehavior">  
  <bamClientBehaviorExtension ConnectionString="Integrated Security=SSPI;Initial Catalog=BAMPrimaryImport;Data Source=.;  Enlist=false"  PollingIntervalSec="1500" />  
</behavior>  
```  
  
## <a name="open-wcf-channel-before-sending-a-message-when-bam-interceptors-are-used"></a>Abrir el canal WCF antes de enviar un mensaje cuando se usan interceptores BAM  
 Cuando el interceptor BAM se habilita para WCF con vinculación BasicHttp, el proxy debe llamar a proxy.Open() para abrir el canal explícitamente. Si el canal no se abre de forma explícita, la interceptación BAM puede fallar con una excepción.
---
title: Consumir servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237868"
---
# <a name="consuming-wcf-services"></a>Consumir servicios WCF
El consumo de servicios WCF le habilita para agregar servicios WCF existentes al proceso empresarial. Es posible agregar varios servicios WCF a una única orquestación.  
  
 Por medio del Asistente para consumición del Servicio WCF de BizTalk, puede consumir (llamar) a un Servicio WCF desde la orquestación. Este Asistente crea los tipos de mensaje y de puerto necesarios para consumir servicios WCF. Además, el Asistente para consumición del Servicio WCF de BizTalk crea dos archivos de enlace que se pueden importar utilizando el asistente o la herramienta de línea de comandos de desarrollo con el fin de configurar puertos de envío con el adaptador personalizado de WCF y los adaptadores de WCF proporcionados por el sistema. El asistente permite usar encabezados SOAP con un servicio WCF consumido, cambiar el URI de un servicio WCF consumido y establecer de forma dinámica el WCF para un servicio web consumido. Los adaptadores de envío WCF consumen servicios WCF y las publicaciones de recepción WCF publican servicios WCF.  
  
 Los adaptadores de envío de WCF de BizTalk incluyen cinco adaptadores de envío físicos que representan los enlaces predefinidos de WCF **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, y **NetMsmqBinding**. Asimismo, los adaptadores de WCF de BizTalk incorporan los adaptadores personalizados que permiten configurar libremente la información de comportamiento y enlace de WCF en un puerto de envío. Para obtener más información acerca de cómo configurar un controlador de envío WCF y el puerto de envío, vea los temas "Cómo..." para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Adaptadores de envío de consideraciones al consumir servicios WCF con WCF](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [Cómo controlar los contratos con tipos erróneos en orquestaciones](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [Especificar acciones SOAP para WCF adaptadores de envío](../core/specifying-soap-actions-for-wcf-send-adapters.md)
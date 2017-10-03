---
title: Configurar los adaptadores de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-wcf-adapters"></a>Configurar adaptadores de WCF
Los adaptadores de BizTalk para Windows Communication Foundation (WFC) permiten que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunique con aplicaciones basadas en WCF. Los adaptadores de WCF de BizTalk incluyen cinco adaptadores físicos que representan los enlaces predefinidos de WCF:**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**,  **NetNamedPipeBinding**, y **NetMsmqBinding**. Se proporcionan adaptadores de WCF para los enlaces predefinidos para permitir configurar de forma sencilla la información necesaria para la mayoría de los requisitos de la aplicación.  
  
 Asimismo, los adaptadores de WCF de BizTalk incorporan dos adaptadores que permiten configurar libremente la información de comportamiento y el enlace de WCF para la ubicación de recepción y el puerto de envío.  
  
 Todos los adaptadores de WCF proporcionan cuadros de diálogo de propiedades de transporte similares para los puertos de envío y las ubicaciones de recepción. Sin embargo, las tareas detalladas para configurar los adaptadores de WFC varían en función del adaptador físico. Las tareas que no están directamente relacionadas con los enlaces del adaptador, como la instalación de certificados, son las mismas para todos los adaptadores de WCF. Esta sección trata las tareas comunes a todos los adaptadores de WFC. Para obtener información acerca de las tareas que difieren para cada adaptador, vea los temas correspondientes para el adaptador en [adaptadores de WCF](../core/wcf-adapters.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [Recomendaciones de seguridad de los adaptadores WCF](../core/wcf-adapters-security-recommendations.md)  
  
-   [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [Cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [Contadores de rendimiento de los adaptadores WCF](../core/wcf-adapters-performance-counters.md)  
  
-   [Compatibilidad de inicio de sesión único para los adaptadores de WCF](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a>Vea también  
 [Adaptadores de WCF](../core/wcf-adapters.md)
---
title: 'Arquitectura de ejemplo: Message Queue Server de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f38d373680fd1b47722fc1ac52c56b113ef59cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269796"
---
# <a name="sample-architecture-biztalk-message-queuing"></a>Arquitectura de ejemplo: Message Queue Server de BizTalk
En esta tema se describe la arquitectura de ejemplo cuando se usa el adaptador de BizTalk para Message Queue Server para enviar y recibir mensajes.  
  
 La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de Message Queue Server de BizTalk.  
  
 **Figura 1: arquitectura de ejemplo que muestra el adaptador de Message Queue Server de BizTalk**  
  
 ![Ejemplo de arquitectura para Message Queue Server de BizTalk](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")  
  
 Esta arquitectura de ejemplo contiene los componentes que se analizan en las secciones siguientes.  
  
## <a name="perimeter-networkinternet"></a>Red perimetral-Internet  
 No se recomienda utilizar el protocolo binario de Message Queue Server en Internet. No debe permitir que cualquier tráfico de Message Queue Server a través del Firewall 1. Si desea utilizar el adaptador de BizTalk para Message Queue para recibir mensajes a través de Internet, haga lo siguiente:  
  
-   Utilice un servidor de Message Queue Server en la red perimetral.  
  
-   Utilice el protocolo HTTP de Message Queue Server en Internet.  
  
-   Coloque una aplicación de reenvío en la red perimetral para que obtenga los mensajes del servidor de Message Queue Server y los reenvíe al adaptador de Message Queue Server de BizTalk mediante un protocolo binario.  
  
    > [!IMPORTANT]
    >  Mantenga cerrados los puertos del servidor de seguridad 1 que usa Message Queue Server de BizTalk aunque lo utilice para recibir mensajes de Internet.  
  
## <a name="perimeter-networkintranet"></a>Red perimetral: intranet  
 Si se utiliza el adaptador de BizTalk para Message Queue Server para recibir mensajes de la intranet, un servidor de Message Queue Server de Windows reenviará el tráfico de Message Queue Server al servidor de BizTalk Server que ejecuta una instancia de host del adaptador de Message Queue Server de BizTalk.  
  
 Si los dominios de intranet y de negocio electrónico comparten un Active Directory común, los mensajes atraviesan una serie de enrutadores de Message Queue Server hasta alcanzar su destino (el servidor BizTalk Server que ejecuta una instancia de host del adaptador de recepción de Message Queue Server de BizTalk). Esta opción no aparece representada en el diagrama porque es menos segura que la primera.  
  
## <a name="e-business-domain"></a>Dominio de negocio electrónico  
 Los servidores de este domino son:  
  
-   **BizTalk Server (procesamiento, adaptador de Message Queue Server de BizTalk y hosts de seguimiento).** Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales. Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes. Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio. Asimismo, este host contiene instancias del host que ejecutan los adaptadores de recepción y envío de Message Queue Server de BizTalk.  
  
    > [!NOTE]
    >  A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.  
  
-   **Servidor secreto principal.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Servidor SQL Server.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Controlador de dominio.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Herramientas de administración.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)
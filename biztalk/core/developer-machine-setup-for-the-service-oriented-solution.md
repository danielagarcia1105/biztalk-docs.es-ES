---
title: Solución orientada a servicios de configuración del equipo del desarrollador del servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb3407dbccbc4dccc902892cf04fa71991b8d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239460"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a>Configuración del equipo del programador para la solución orientada a servicios
La arquitectura orientada a servicios (SOA) es un enfoque para la generación de sistemas distribuidos. La solución orientada a servicios demuestra cómo varios sistemas servidor con protocolos distintos se pueden integrar en un único servicio que pueden consumir los clientes. Esta solución integra servicios con un enfoque que garantiza características de entrega y rendimiento para los acuerdos de nivel de servicio que tiene que satisfacer.  
  
 La solución orientada a servicios basa su modelo en un escenario de contrato de nivel de servicio en el que BizTalk Server y los servidores de la aplicación de la unidad de negocio conectados a éste disponen de tres segundos para responder a una solicitud de servicio. Uno de estos tres segundos puede ser utilizado por el servidor BizTalk Server.  
  
 Hay tres versiones de la solución orientada a servicios: adaptador, en línea y el código auxiliar. Para obtener más información acerca de las diferencias entre las tres versiones de la solución orientada a servicios, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md). Como un programador, obtiene que se esté ejecutando el escenario utilizando la versión de código auxiliar del escenario. Esta versión no requiere ningún servidor LOB para ejecutarse. Después, podrá utilizar la versión del adaptador del escenario para conocer cómo pueden integrarse y configurarse varios adaptadores y servidores para responder mediante los servidores de BizTalk Server como un único servicio. A continuación, puede medir la latencia inducida por BizTalk Server y sus adaptadores.  
  
 Si existe un exceso de latencia de BizTalk Server en sus requisitos de servicios, puede omitir los puntos de persistencia del adaptador LOB mediante la instalación y ejecución de la versión en línea de SOA. Esta versión omite los adaptadores y, en consecuencia, sus contribuciones de latencia debido al punto de persistencia del cuadro de mensajes. En su lugar, la versión en línea se comunica de inmediato con los servidores a través de mecanismos de autenticación de llamadas a procedimiento remoto (RPC) como DCOM.  
  
 Para obtener más información sobre el punto de persistencia de cuadro de mensajes, vea [persistencia y el motor de orquestaciones](../core/persistence-and-the-orchestration-engine.md).  
  
 Esta guía de implementación describe el modo de instalación y prueba de las tres versiones de la solución orientada a servicios en un único equipo.  
  
 Para obtener más información acerca de la solución orientada a servicios, vea [descripción de la solución orientada a servicios](../core/understanding-the-service-oriented-solution.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md)  
  
-   [Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [Cómo ejecutar el servicio de la solución orientada a servicios](../core/how-to-run-the-service-oriented-solution.md)
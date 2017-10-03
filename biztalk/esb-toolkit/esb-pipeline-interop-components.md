---
title: "Los componentes de interoperabilidad de canalización ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf4d4353e6928b998d31e8096ee642cd80bb60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="esb-pipeline-interop-components"></a>Componentes de interoperabilidad de canalización ESB
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona compatibilidad con componentes y servicios, incluidos los siguientes:  
  
-   **Componentes de canalización JMS.** Estos componentes reconocerán, validar y exponen los metadatos y el contenido de los mensajes que se ajusta al formato de JMS MQRFH2 utilizado por los sistemas de mensajería de IBM MQ Series. Esta funcionalidad permite un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación para recibir mensajes desde y enviar mensajes a sistemas JMS en MQ Series. Los componentes automáticamente promoción la información de encabezado en y disminuir el nivel del contenido del mensaje.  
  
-   **Componentes de canalización de Namespace.** Estos componentes pueden agregar o quitar espacios de nombres en el contenido de los mensajes XML. Esto permite a las aplicaciones reparar los espacios de nombres en conflicto o agregar espacios de nombres que faltan para evitar conflictos de espacio de nombres dentro de las orquestaciones de aplicación y de base de datos de cuadro de mensaje. Los componentes también permiten que el servidor BizTalk Server consumir POX (Plain Old XML) sin modificar de sistemas externos de publicación.  
  
 Para obtener más información acerca de los componentes de canalización ESB, consulte [con los componentes de compatibilidad de canalización](../esb-toolkit/using-the-pipeline-support-components.md).
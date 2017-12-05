---
title: "Marco de administración de excepciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4d4d19caebb667e822b15b937d9045a26493a57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="exception-management-framework"></a>Marco de administración de excepciones
El marco de trabajo de administración de excepciones de ESB proporciona un mecanismo de generación de errores orientado a mensajes unificada para administrar todas las excepciones que pueden aparecer en un entorno de BizTalk Server. El marco de trabajo de administración de excepciones de ESB puede recibir mensajes de excepción publicados a través del servicio de publicación de excepción, además de mensajes desde el mecanismo de BizTalk Server no se pudo enrutamiento de mensajes.  
  
 El marco de trabajo proporciona una API para la creación de mensajes de error, la publicación y la administración de procesos de orquestación, la replicación de la característica de enrutamiento de mensajes con errores de BizTalk Server se introdujo por primera vez con BizTalk Server 2006. Además, el marco de trabajo proporciona funciones para la normalización de todas las excepciones, enriquecer, aplicar el seguimiento de supervisión de la actividad económica (BAM) y publicar el resultado final en la base de datos de administración de excepciones para su presentación y los informes en ESB Portal de administración.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes componentes de canalización que admiten el marco de administración de excepciones de ESB:  
  
-   **Componente de canalización de procesador de error de excepción.** Este componente se incluye como parte de la canalización asociada con la excepción de ESB fuera de rampa. Desactivar este aumento se suscribe a todos los mensajes de error generados por ESB, además de las excepciones que genera el mensaje error de BizTalk Server mecanismo de enrutamiento. Mensajes a la base de datos de Portal de administración de ESB de administración de ESB excepción de error de las rutas de componente, o se puede configurar para el enrutamiento a otra ubicación. El componente de canalización también enriquece todos los mensajes de error y excepciones con metadatos y ellos normaliza a un formato común.  
  
-   **Componente de canalización de seguimiento de BAM.** Este componente intercepta y registra la información de excepción en el subsistema de BAM de BizTalk Server y se utiliza exclusivamente por la canalización del procesador de error de excepción en el marco de trabajo de administración de excepciones. Proporcionará [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es un ejemplo que muestra cómo utilizar BAM como una instalación opcional de seguimiento para obtener información de excepción.  
  
 Para obtener más información sobre el marco de trabajo de administración de excepciones, vea [utilizando Administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).
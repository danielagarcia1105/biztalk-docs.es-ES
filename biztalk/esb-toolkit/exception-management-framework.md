---
title: Marco de administración de excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b5aebc0-2467-4f48-a385-056507ed1c1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc334dd93c0ad53737b1fe36d50355cecae565a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017846"
---
# <a name="exception-management-framework"></a>Marco de administración de excepciones
El marco de administración de excepciones de ESB proporciona un mecanismo de generación de errores orientado a mensajes unificada para administrar todas las excepciones que pueden producirse en un entorno de BizTalk Server. El marco de administración de excepciones de ESB puede recibir mensajes de excepción que se publican a través del servicio de publicación de excepción, además de los mensajes del mecanismo de BizTalk Server no se pudo enrutamiento de mensajes.  
  
 El marco de trabajo proporciona una API para la creación de mensajes de error, la publicación y administración de procesos de orquestación, la replicación de la característica de enrutamiento de mensajes con errores de BizTalk Server se introdujo por primera vez con BizTalk Server 2006. Además, el marco de trabajo proporciona funciones para la normalización de todas las excepciones, enriquecer, aplicar el seguimiento de la supervisión de la actividad económica (BAM) y publicar el resultado final en la base de datos de administración de excepciones para su presentación y los informes en el ESB Portal de administración.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye los siguientes componentes de canalización que admiten el marco de administración de excepciones de ESB:  
  
- <strong>Componente de canalización de procesador de error de excepción.</strong> Este componente se incluye como parte de la canalización asociada con la excepción de ESB fuera de rampa. Esta fuera de rampa se suscribe a todos los mensajes de error generados por ESB, además de las excepciones generadas por el mensaje con errores de BizTalk Server mecanismo de enrutamiento. Mensajes a la base de datos de Portal de administración de ESB de administración de ESB excepción de error de las rutas de componente, o puede configurarse para enrutar a otra ubicación. El componente de canalización también enriquece todos los mensajes de error y excepciones con metadatos y normaliza a ellos en un formato común.  
  
- <strong>Componente de canalización de seguimiento de BAM.</strong> Este componente intercepta y registra la información de excepción en el subsistema de BAM de BizTalk Server y sea utilizado exclusivamente por la canalización del procesador de errores de excepción dentro del marco de administración de la excepción. Se valió [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] es un ejemplo que muestra cómo utilizar BAM como una instalación opcional de seguimiento para obtener información de excepción.  
  
  Para obtener más información sobre el marco de administración de excepciones, vea [usando administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).
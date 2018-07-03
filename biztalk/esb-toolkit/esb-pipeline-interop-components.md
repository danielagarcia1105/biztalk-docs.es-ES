---
title: Los componentes de interoperabilidad de canalización ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 794ce6407d10fc820444384550357f10d24f7723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024250"
---
# <a name="esb-pipeline-interop-components"></a>Componentes de interoperabilidad de canalización ESB
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona componentes de soporte técnico y servicios, incluidos los siguientes:  
  
- **Componentes de canalización JMS.** Estos componentes reconocerán, validación y exponen los metadatos y el contenido de los mensajes que cumplen el formato de MQRFH2 de JMS usado por los sistemas de mensajería de IBM MQ Series. Esta funcionalidad permite una [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación para recibir mensajes desde y enviar mensajes a sistemas JMS a través de MQ Series. Los componentes automáticamente promoción la información de encabezado en y disminuir el nivel del contenido del mensaje.  
  
- **Componentes de canalización de Namespace.** Estos componentes pueden agregar o quitar espacios de nombres en el contenido de los mensajes XML. Esto permite que las aplicaciones reparar los espacios de nombres en conflicto o agregar espacios de nombres que faltan para evitar conflictos de espacio de nombres dentro de las orquestaciones de aplicación y de base de datos de cuadro de mensaje. Los componentes también permiten a BizTalk Server consumir POX (Plain Old XML) sin modificar los sistemas externos de publicación.  
  
  Para obtener más información acerca de los componentes de canalización ESB, consulte [mediante los componentes de soporte técnico de canalización](../esb-toolkit/using-the-pipeline-support-components.md).
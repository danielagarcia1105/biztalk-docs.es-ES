---
title: Problemas conocidos con las entidades EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86475960-cdb2-4b39-817a-b5d834f498a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fddda6dd62e8e3bd2d38574343b7fcb0e0d76f89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261788"
---
# <a name="known-issues-with-edi-parties"></a>Problemas conocidos de las entidades EDI
Esta sección contiene temas que describen los problemas conocidos relacionados con las entidades EDI y el administrador de acuerdos de socios comerciales.  
  
## <a name="a-cache-refresh-period-delays-availability-of-a-changed-party-property"></a>Un periodo de actualización de caché retrasa la disponibilidad de una propiedad de entidad cambiada  
 Si cambia una propiedad global o de entidad en PAM, las propiedades estarán disponibles para el tiempo de ejecución de BizTalk después de que la memoria caché se actualice cada quince minutos o después de reiniciar el servicio de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Configurar confirmaciones EDI](../core/configuring-edi-acknowledgments.md)   
 [Rol de los acuerdos en el procesamiento de EDI](../core/the-role-of-agreements-in-edi-processing.md)   
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)   
 [Configurar propiedades del acuerdo de reserva o globales](../core/configuring-global-or-fallback-agreement-properties.md)
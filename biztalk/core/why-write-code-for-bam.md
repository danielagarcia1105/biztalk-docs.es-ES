---
title: ¿Por qué escribir código para BAM? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434f50a-e0a9-45e0-8c68-a059011e1296
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8830a2076e460f83440f38080d2e8cd60abf9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982205"
---
# <a name="why-write-code-for-bam"></a>¿Por qué escribir código para BAM?
En la mayoría de las circunstancias puede usar las herramientas de BAM sin que sea necesario escribir su propio código para realizar funciones de seguimiento. Estas herramientas son el complemento de BAM para Excel, la utilidad de administración de BAM y el Editor de perfiles de seguimiento (TPE). BAM en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona interceptores para las orquestaciones y componentes de mensajería de BizTalk (canalizaciones y puertos). Un interceptor es software que instrumenta una aplicación para que pueda recopilar datos de un modo genérico basado en un archivo de configuración. Puede instrumentar la aplicación para que use estos interceptores mediante el Editor de perfiles de seguimiento. Para obtener más información sobre el Editor de perfiles de seguimiento, vea [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md).  
  
 Sin embargo, hay dos escenarios principales en los que le resultará ventajoso instrumentar su aplicación mediante las API de BAM:  
  
- No existe un interceptor de BAM para el host que pretende supervisar.  
  
- El interceptor integrado no permite la complejidad de la aplicación.  
  
  Cuando no hay ningún interceptor integrado, puede usar BAM **EventStream** API para capturar los eventos de interés.  
  
> [!NOTE]
>  Puede combinar **EventStream** clases con el **BAMInterceptor** clase para crear su propio interceptor. El ejemplo de SDK de API de BAM ilustra un interceptor genérico simple que puede extender. Al construir su propio interceptor, puede instrumentar varios procesos similares sin tener que escribir código nuevo para cada aplicación. Para ver el ejemplo de SDK de API de BAM, consulte [API de BAM (ejemplo de BizTalk Server)](../core/bam-api-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Implementar soluciones de BAM](../core/implementing-bam-solutions.md)
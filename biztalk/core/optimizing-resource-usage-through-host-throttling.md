---
title: Optimizar el uso de recursos mediante la limitación de Host | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263612"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a>Optimizar el uso de recursos mediante la limitación de host
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]hace uso de diferentes tecnologías de Microsoft, cada uno de los cuales puede consumir una parte importante de la memoria, disco y recursos de CPU disponibles en el servidor BizTalk server y SQL server que contiene las bases de datos de BizTalk Server. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]emplea un mecanismo de limitación para ayudar a administrar el uso de recursos disponibles para minimizar la contención de uso de recursos. En este tema se describe el diseño de este mecanismo. Para obtener información sobre cómo ajustar los valores de limitación, consulte [uso del panel de configuración para la optimización de rendimiento de BizTalk Server](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Qué es la limitación de Host?](../core/what-is-host-throttling.md)  
  
-   [Cómo BizTalk Server incorpora la limitación de Host](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [Contadores de rendimiento de limitación de host](../core/host-throttling-performance-counters.md)  
  
-   [Recomendaciones de diseño de limitación](../core/throttling-design-recommendations.md)
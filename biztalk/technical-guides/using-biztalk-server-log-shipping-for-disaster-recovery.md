---
title: Mediante la recuperación ante desastres de trasvase de registros de servidor BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2ded5686cc81b1cc3b629601b142a19c3b7b193
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023386"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>Uso de recuperación ante desastres de trasvase de registros de servidor BizTalk Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementa la base de datos en espera capacidades mediante el uso de la base de datos de trasvase de registros. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] el trasvase de registros automatiza la copia de seguridad y restauración de archivos de registro de transacciones y la base de datos, lo que permite a un servidor en espera reanudar el procesamiento de base de datos en caso de que se produce un error en el servidor de base de datos de producción.  
  
## <a name="how-log-shipping-works"></a>Cómo funciona de trasvase de registros  
 El [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] utilizados por los trabajos del agente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de trasvase de registros a sincronizar datos entre el servidor de origen utilizados en la producción y el servidor de destino que se usa como un servidor en espera cada 15 minutos de forma predeterminada (es decir, cada vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server).  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>Uso de recuperación ante desastres de trasvase de registros  
 Haga lo siguiente al usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros para la recuperación ante desastres:  
  
- Siga los pasos descritos en el tema [lista de comprobación: aumento de disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) para aumentar la disponibilidad de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres.  
  
- Compruebe que los servidores de recuperación ante desastres tienen la capacidad para administrar la carga de producción.  
  
   Asegúrese de que los servidores en espera tienen el mismos o similares recursos disponibles (CPU/memoria/disco) como los servidores de producción.  
  
- Asegúrese de que los detalles de la rutina de recuperación ante desastres están bien documentados.  
  
   Documente todos los pasos de la preparación de la recuperación ante desastres y la implementación en detalle. Ante desastres rara vez huelgas cuando sea conveniente por lo que se suponen que las partes responsables de implementar el procedimiento de recuperación ante desastres están comenzando a su primer día de trabajo y a realizar esto por primera vez.  
  
- Como parte de la prueba, práctica conmutación por error normal para el sitio de recuperación ante desastres, especialmente como nuevo de BizTalk se colocan las aplicaciones en producción.  
  
   Realizar las pruebas como parte de las pruebas y el mantenimiento para asegurarse de que puede realizar sin problemas normal de conmutación por error.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)
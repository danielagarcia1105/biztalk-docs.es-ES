---
title: "Supervisión de bases de datos de servidor BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fee5015-e818-459b-aeeb-a084ef355600
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fed740f0c2689c8c531a2f92ad4be356d82205db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-biztalk-server-databases"></a>Supervisión de las bases de datos de servidor BizTalk Server
Puede ejecutar el trabajo de agente de SQL Server de BizTalk de Monitor para identificar todos los problemas conocidos en las bases de datos de administración, el cuadro de mensaje o DTA. El trabajo se crea al configurar un grupo de BizTalk en la consola de administración de BizTalk Server o al actualizar la versión anterior de BizTalk.  
  
## <a name="the-monitor-biztalk-server-job"></a>El trabajo del Monitor de servidor BizTalk Server  
 El trabajo Supervisar BizTalk Server busca los siguientes problemas en la administración, el cuadro de mensaje y las bases de datos DTA:  
  
> [!NOTE]  
>  El trabajo Supervisar BizTalk Server solo busca los problemas. No arregla los problemas que encuentra.  
  
-   Mensajes sin referencias  
  
-   Mensajes sin números de referencia  
  
-   Mensajes con número de referencia menor que 0  
  
-   Referencias de mensajes sin filas de colas de trabajo  
  
-   Referencias de mensaje sin instancias  
  
-   Estado de instancia sin instancias  
  
-   Suscripciones de instancia sin instancias correspondientes  
  
-   Instancias de servicio DTA huérfano  
  
-   Excepciones de instancia de servicio DTA huérfano  
  
-   TDDS no se ejecuta en cualquier instancia de host cuando está habilitada la opción de seguimiento global  
  
 El trabajo Supervisar BizTalk Server está configurado y automatizado para ejecutarse una vez a la semana. Puesto que el trabajo es computacionalmente intensivo, se recomienda programarlo para que se ejecute durante los períodos de tiempo de inactividad o poco tráfico.  
El trabajo se produce un error si encuentra algún problema; la cadena de error que se devuelve contiene el número de problemas encontrados. Si no, se ejecuta correctamente. Puede ver los detalles en el historial del trabajo. Si el trabajo se ejecuta con privilegios de administrador, la cadena de error se registrará en el historial de trabajos y el registro de aplicación de SQL Server.  
  
> [!IMPORTANT]  
>  Error de este trabajo no constituye necesariamente un problema crítico, pero en su lugar un problema que se debe investigar y dirigirse como parte del mantenimiento regular de las bases de datos de BizTalk Server. Este trabajo no tiene éxito por cuestiones de diseño en caso de que detecta uno de los problemas mencionados anteriormente.
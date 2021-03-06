---
title: Supervisar las bases de datos de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f137fc5-0e95-4952-8465-008771a1a377
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b041822791b08890a34c39f3658de879062d9fb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973821"
---
# <a name="monitor-the-biztalk-server-databases"></a>Supervisar las bases de datos de BizTalk Server
Puede ejecutar el trabajo del Agente SQL de supervisar BizTalk Server para identificar los problemas conocidos de las bases de datos de administración, el cuadro de mensaje o DTA. El trabajo se crea al configurar un grupo de BizTalk en la consola de administración de BizTalk Server o al actualizar la versión anterior de BizTalk.  
  
## <a name="the-monitor-biztalk-server-job"></a>El trabajo del Monitor de servidor BizTalk Server  
 El trabajo Supervisar BizTalk Server busca los siguientes problemas en la administración, el cuadro de mensaje y las bases de datos DTA:  
  
> [!NOTE]  
>  El trabajo Supervisar BizTalk Server solo busca los problemas. No arregla los problemas que encuentra.  
  
- Mensajes sin referencias  
  
- Mensajes sin números de referencia  
  
- Mensajes con número de referencia menor que 0  
  
- Referencias de mensajes sin filas de colas de trabajo  
  
- Referencias de mensaje sin instancias  
  
- Estado de instancia sin instancias  
  
- Suscripciones de instancia sin instancias correspondientes  
  
- Instancias de servicio DTA huérfano  
  
- Excepciones de instancia de servicio DTA huérfano  
  
- TDDS no se está ejecutando en cualquier instancia de host cuando está habilitada la opción de seguimiento global  
  
  El trabajo Supervisar BizTalk Server está configurado y automatizado para ejecutarse una vez a la semana. Puesto que el trabajo es computacionalmente intensivo, se recomienda programarlo para que se ejecutan durante períodos de tiempo de inactividad o de poco tráfico.  
  El trabajo se produce un error si encuentra algún problema; la cadena de error devuelta contiene el número de los problemas encontrados. Si no, se ejecuta correctamente. Puede ver los detalles en el historial del trabajo. Si se ejecuta el trabajo con privilegios de administrador, la cadena de error se registrará en el historial de trabajos y el registro de aplicación de SQL Server.  
  
> [!IMPORTANT]  
>  Error de este trabajo no necesariamente constituye un problema crítico, pero en su lugar un problema que se debe investigar y dirigirse como parte del mantenimiento regular de las bases de datos de BizTalk Server. Este trabajo no tiene éxito por diseño, en caso de que detecta uno de los problemas mencionados anteriormente. Para obtener más información acerca de los problemas mencionados anteriormente y para tener acceso a las utilidades que se usan habitualmente por servicios de soporte técnico de Microsoft para solucionar estos problemas, consulte la sección [utilizando el terminador de BizTalk para resolver los problemas identificados por BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=210367) (http://go.microsoft.com/fwlink/?LinkId=210367).
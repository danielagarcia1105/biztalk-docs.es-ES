---
title: Datos almacenados para informes de estado de AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14fc95dfba5e29089653ef02dddd1b0b366ff8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012519"
---
# <a name="data-stored-for-as2-status-reports"></a>Datos almacenados para informes de estado de AS2
Existen dos niveles de informes están disponibles en informes de estado AS2: el primero tiene lugar si el **activar informes** propiedad está seleccionada para un acuerdo (desde el **propiedades generales** página de la **General**  pestaña en el **las propiedades del acuerdo** cuadro de diálogo) y el segundo si está seleccionada una propiedad de almacenamiento de base de datos sin repudio para un acuerdo.  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a>Datos que se almacenan si están activados los informes AS2  
 Si el **activar informes** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mantendrá un registro de todos los enviado o recibido mensajes AS2 y MDN.  
  
 En el caso de mensajes AS2 recibidos, BizTalk Server almacenará los siguientes datos:  
  
- Un registro del mensaje AS2.  
  
  En el caso de MDN enviados o recibidos (sincrónico o asíncrono), BizTalk Server almacenará los datos siguientes:  
  
- Un registro del MDN.  
  
  La interfaz de usuario de los informes de estado habilita la correlación del registro del mensaje AS2 con el registro del MDN correspondiente.  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a>Datos que se almacenan si está habilitado Reenviar mensaje de AS2 si no se recibe MDN  
 Si el **reenviar mensaje AS2 si no se recibe MDN** propiedad está seleccionada para un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] registrará la siguiente información:  
  
-   Fecha y hora de cada intento de reenvío  
  
-   Estado de cada intento de reenvío  
  
-   Índice de cada intento de reenvío  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a>Datos que se almacenan si está habilitado el almacenamiento de la base de datos sin repudio  
 El almacenamiento de la base de datos sin repudio se habilita seleccionando las propiedades del acuerdo siguientes:  
  
- NRR habilitado para mensajes AS2 codificados de salida  
  
- NRR habilitado para mensajes AS2 descodificados de salida  
  
- NRR habilitado para MDN de entrada  
  
- NRR habilitado para mensajes de AS2 codificados de entrada  
  
- NRR habilitado para mensajes de AS2 descodificados de entrada  
  
- NRR habilitado para MDN de salida  
  
  Si está seleccionada una o varias de las propiedades anteriores, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] almacenará los datos siguientes:  
  
- El contenido de todos los mensajes AS2 y el de todos los MDN (con o sin encabezados AS2).  
  
## <a name="data-stored-for-edi-over-as2"></a>Datos almacenados para mensajes EDI a través de transporte AS2  
 Si el **activar informes** está seleccionada la propiedad tanto para un acuerdo de EDI, así como un acuerdo de AS2 y, después, puede poner en correlación un registro de mensaje AS2 (que contiene la carga EDI) con un registro de mensaje EDI.  
  
 Si está habilitado el almacenamiento de conjuntos de transacciones, es posible mostrar los detalles de los conjuntos de transacciones y los detalles del contenido de los mensajes AS2 en la interfaz de usuario del informe de estado.  
  
> [!NOTE]
>  Para obtener acceso a estos informes, debe utilizar las canalizaciones AS2EdiReceive o AS2EdiSend.  
  
## <a name="see-also"></a>Vea también  
 [Datos almacenados para informes de estado de AS2 y EDI](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [Datos almacenados para informes de estado EDI](../core/data-stored-for-edi-status-reports.md)   
 [Datos almacenados para informes de estado de procesamiento por lotes](../core/data-stored-for-batching-status-reports.md)
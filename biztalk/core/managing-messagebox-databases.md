---
title: Administrar bases de datos de cuadro de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e854ad0f7014de8241f8a7b6af6addd49cb4da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262148"
---
# <a name="managing-messagebox-databases"></a>Administrar bases de datos de cuadro de mensajes
La base de datos de cuadro de mensajes tiene tres funciones básicas. Almacena suscripciones e información de seguimiento, y entrega los mensajes a los servicios que coinciden con las suscripciones. La base de datos de cuadro de mensajes es una plataforma de host que almacena las colas y tablas de estado de cada host de BizTalk. La base de datos de cuadro de mensajes almacena también mensajes y propiedades.  
  
 Si las bases de datos de cuadro de mensajes son un activo con una exposición de alto riesgo en su entorno, se recomienda usar el protocolo de seguridad de Internet (IPSec) o Capa de sockets seguros (SSL) para restringir y proteger la comunicación con las bases de datos de cuadro de mensajes.  
  
 Si utiliza Windows Server 2003, debe habilitar el Coordinador de transacciones distribuidas (DTC) en la base de datos de cuadro de mensajes. También debe habilitar los clientes de red para implementaciones de varios equipos. Para obtener más información, consulte [puertos para el servidor de administración](../core/ports-for-the-administration-server.md).  
  
 Esta sección contiene información de procedimientos para administrar las bases de datos de cuadro de mensajes en su entorno. Para obtener información conceptual acerca de las bases de datos de cuadro de mensajes y la suscripción del modelo de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza para procesar mensajes, vea [la base de datos de cuadro de mensajes](../core/the-messagebox-database.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo agregar una nueva base de datos de cuadro de mensajes](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [Cómo deshabilitar la publicación de mensajes nuevos](../core/how-to-disable-new-message-publication.md)  
  
-   [Cómo eliminar una base de datos de cuadro de mensajes](../core/how-to-delete-a-messagebox-database.md)
---
title: Publicar puntos de conexión de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e8cc81-c6c7-4269-81e3-8725082a0c98
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33517f1261324ad01eb0d9cad0f51b74c280828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294292"
---
# <a name="publishing-biztalk-endpoints"></a>Publicación de extremos de BizTalk
Puede usar el Portal de administración de ESB para crear y publicar entradas en el servidor de Universal Description, Discovery y Integration (UDDI) configurado en ese momento.  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a>Para publicar un punto de conexión de Microsoft BizTalk Server en el servidor actual de UDDI  
  
1.  Seleccione el **registro** pestaña en el menú principal portal y, a continuación, haga clic en **nueva entrada del registro** para abrir el [nueva página de entrada de registro](../esb-toolkit/new-registry-entry-page.md).  
  
2.  Utilice las listas de lista desplegable en la página para filtrar según el tipo de punto de conexión, el estado y la aplicación en el que reside el punto de conexión.  
  
3.  Haga clic en el icono de flecha situado junto al punto de conexión que desea publicar para crear una solicitud de registro UDDI.  
  
4.  Si un administrador ha habilitado la publicación automática de puntos de conexión, el portal publica automáticamente la nueva entrada en el servidor UDDI.  
  
5.  Si un administrador no ha habilitado la publicación automática de puntos de conexión, las solicitudes permanece en la cola hasta que un administrador apruebe o rechace la solicitud.
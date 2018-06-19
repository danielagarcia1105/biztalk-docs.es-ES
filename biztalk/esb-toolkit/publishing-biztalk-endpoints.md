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
# <a name="publishing-biztalk-endpoints"></a><span data-ttu-id="58ebb-102">Publicación de extremos de BizTalk</span><span class="sxs-lookup"><span data-stu-id="58ebb-102">Publishing BizTalk Endpoints</span></span>
<span data-ttu-id="58ebb-103">Puede usar el Portal de administración de ESB para crear y publicar entradas en el servidor de Universal Description, Discovery y Integration (UDDI) configurado en ese momento.</span><span class="sxs-lookup"><span data-stu-id="58ebb-103">You can use the ESB Management Portal to create and publish entries into the currently configured Universal Description, Discovery, and Integration (UDDI) server.</span></span>  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a><span data-ttu-id="58ebb-104">Para publicar un punto de conexión de Microsoft BizTalk Server en el servidor actual de UDDI</span><span class="sxs-lookup"><span data-stu-id="58ebb-104">To publish a Microsoft BizTalk Server endpoint into the current UDDI server</span></span>  
  
1.  <span data-ttu-id="58ebb-105">Seleccione el **registro** pestaña en el menú principal portal y, a continuación, haga clic en **nueva entrada del registro** para abrir el [nueva página de entrada de registro](../esb-toolkit/new-registry-entry-page.md).</span><span class="sxs-lookup"><span data-stu-id="58ebb-105">Point to the **Registry** tab on the portal main menu, and then click **New Registry Entry** to open the [New Registry Entry Page](../esb-toolkit/new-registry-entry-page.md).</span></span>  
  
2.  <span data-ttu-id="58ebb-106">Utilice las listas de lista desplegable en la página para filtrar según el tipo de punto de conexión, el estado y la aplicación en el que reside el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="58ebb-106">Use the drop-down lists on the page to filter on the endpoint type, the status, and the application where the endpoint resides.</span></span>  
  
3.  <span data-ttu-id="58ebb-107">Haga clic en el icono de flecha situado junto al punto de conexión que desea publicar para crear una solicitud de registro UDDI.</span><span class="sxs-lookup"><span data-stu-id="58ebb-107">Click the arrow icon next to the endpoint you want to publish to create a UDDI registration request.</span></span>  
  
4.  <span data-ttu-id="58ebb-108">Si un administrador ha habilitado la publicación automática de puntos de conexión, el portal publica automáticamente la nueva entrada en el servidor UDDI.</span><span class="sxs-lookup"><span data-stu-id="58ebb-108">If an administrator has enabled auto-publishing of endpoints, the portal automatically publishes the new entry into the UDDI server.</span></span>  
  
5.  <span data-ttu-id="58ebb-109">Si un administrador no ha habilitado la publicación automática de puntos de conexión, las solicitudes permanece en la cola hasta que un administrador apruebe o rechace la solicitud.</span><span class="sxs-lookup"><span data-stu-id="58ebb-109">If an administrator has not enabled auto-publishing of endpoints, the requests remains in the queue until an administrator approves or declines the request.</span></span>
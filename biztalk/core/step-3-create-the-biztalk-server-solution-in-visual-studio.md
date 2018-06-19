---
title: 'Paso 3: Crear la solución de BizTalk Server en Visual Studio | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4da3333-e430-4caf-bc29-44a60ebac385
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 402434ec74327b55f243fecd9d1c347ce4ff0390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278020"
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a><span data-ttu-id="0569b-102">Paso 3: Crear la solución de BizTalk Server en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0569b-102">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>
<span data-ttu-id="0569b-103">En esta sección, veremos cómo crear la solución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para recibir notificaciones de oportunidades de Salesforce, enviar consultas a Salesforce para obtener información adicional acerca de las oportunidades y, finalmente, insertar esa información en una base de datos de SQL Server local.</span><span class="sxs-lookup"><span data-stu-id="0569b-103">In this section, we look at creating the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution for receiving opportunity notifications from Salesforce, querying Salesforce to get additional information about the opportunity, and finally inserting that information into an on-premise SQL Server database.</span></span> <span data-ttu-id="0569b-104">Esta sección se clasifica de acuerdo con estos pasos más amplios.</span><span class="sxs-lookup"><span data-stu-id="0569b-104">This section is further categorized according to each of these broader steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0569b-105">Para poder enviar y recibir mensajes de Salesforce en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debemos incluir algunos componentes personalizados en nuestra solución.</span><span class="sxs-lookup"><span data-stu-id="0569b-105">To be able to send messages to Salesforce and to receive messages from Salesforce into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], we need to include some custom components into our solution.</span></span> <span data-ttu-id="0569b-106">Creamos esos componentes personalizados en [paso 3d: habilitación de BizTalk Server para enviar y recibir mensajes desde Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span><span class="sxs-lookup"><span data-stu-id="0569b-106">We create those custom components in [Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0569b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0569b-107">In This Section</span></span>  
  
-   [<span data-ttu-id="0569b-108">Paso 3a: recibir una notificación de oportunidad de Salesforce en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0569b-108">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [<span data-ttu-id="0569b-109">Paso 3b: recuperar detalles de oportunidades de Salesforce con el adaptador de WCF-WebHttp</span><span class="sxs-lookup"><span data-stu-id="0569b-109">Step 3b: Retrieve Opportunity Details from Salesforce using the WCF-WebHttp Adapter</span></span>](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [<span data-ttu-id="0569b-110">Paso 3c: Insertar detalles de oportunidades en una base de datos SQL Server</span><span class="sxs-lookup"><span data-stu-id="0569b-110">Step 3c: Insert Opportunity Details into a SQL Server Database</span></span>](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [<span data-ttu-id="0569b-111">Paso 3d: Habilitar BizTalk Server para enviar y recibir mensajes desde Salesforce</span><span class="sxs-lookup"><span data-stu-id="0569b-111">Step 3d: Enabling BizTalk Server to Send and Receive Messages from Salesforce</span></span>](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [<span data-ttu-id="0569b-112">Paso 3e: compilar e implementar la solución de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0569b-112">Step 3e: Build and Deploy the BizTalk Server Solution</span></span>](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="0569b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0569b-113">See Also</span></span>  
 [<span data-ttu-id="0569b-114">Tutorial: 6: Integración de BizTalk Server 2013 con Salesforce</span><span class="sxs-lookup"><span data-stu-id="0569b-114">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)
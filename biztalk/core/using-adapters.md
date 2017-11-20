---
title: Usar adaptadores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters
ms.assetid: afdfa70e-5929-4746-99b4-e76274aa5c88
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18ffc3c198cbd6fc26290908dfcc3a90b2c8a62a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-adapters"></a><span data-ttu-id="a4870-102">Usar adaptadores</span><span class="sxs-lookup"><span data-stu-id="a4870-102">Using Adapters</span></span>
<span data-ttu-id="a4870-103">Esta sección contiene información completa acerca de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="a4870-103">This section contains comprehensive information about adapters.</span></span> <span data-ttu-id="a4870-104">Describe cómo se utilizan los adaptadores en Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y cómo configurar controladores de adaptador, puertos de envío y ubicaciones de recepción para cada adaptador.</span><span class="sxs-lookup"><span data-stu-id="a4870-104">It describes how adapters are used in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and how to configure adapter handlers, send ports, and receive locations for each adapter.</span></span> <span data-ttu-id="a4870-105">Proporciona información de soporte técnico sobre el procesamiento por lotes que le ayuda a entender y a utilizar los adaptadores nativos en su solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4870-105">It provides batching support information to help you understand and use the native adapters in your BizTalk solution.</span></span>  
  
 <span data-ttu-id="a4870-106">Para obtener información sobre cómo usar métodos abreviados de teclado para las páginas de propiedades de adaptador, vea [abreviados de teclado de página de propiedades de adaptador](../core/adapter-property-page-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="a4870-106">For information about using the keyboard shortcuts for the adapter property pages, see [Adapter Property Page Keyboard Shortcuts](../core/adapter-property-page-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4870-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a4870-107">In This Section</span></span>  
  
-   [<span data-ttu-id="a4870-108">Adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a4870-108">Adapters in BizTalk Server</span></span>](../core/adapters-in-biztalk-server.md)  
  
-   [<span data-ttu-id="a4870-109">Controlador de puerto de envío dinámico es Configurable</span><span class="sxs-lookup"><span data-stu-id="a4870-109">Dynamic Send Port Handler is Configurable</span></span>](../core/dynamic-send-port-handler-is-configurable.md)  
  
-   [<span data-ttu-id="a4870-110">Consideraciones de seguridad para los adaptadores</span><span class="sxs-lookup"><span data-stu-id="a4870-110">Security Considerations for Adapters</span></span>](../core/security-considerations-for-adapters.md)  
  
-   [<span data-ttu-id="a4870-111">Adaptador SB-Messaging</span><span class="sxs-lookup"><span data-stu-id="a4870-111">SB-Messaging adapter</span></span>](../core/sb-messaging-adapter.md)  
  
-   [<span data-ttu-id="a4870-112">Adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="a4870-112">File adapter</span></span>](../core/file-adapter.md)  
  
-   [<span data-ttu-id="a4870-113">Adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="a4870-113">FTP adapter</span></span>](../core/ftp-adapter.md)  

- [<span data-ttu-id="a4870-114">Adaptador de aplicación lógica</span><span class="sxs-lookup"><span data-stu-id="a4870-114">Logic App adapter</span></span>](../core/logic-app-adapter.md)
  
-   [<span data-ttu-id="a4870-115">Adaptador SFTP</span><span class="sxs-lookup"><span data-stu-id="a4870-115">SFTP adapter</span></span>](../core/sftp-adapter.md)  
  
-   [<span data-ttu-id="a4870-116">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="a4870-116">HTTP adapter</span></span>](../core/http-adapter.md)  
  
-   [<span data-ttu-id="a4870-117">Adaptador de JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="a4870-117">JD Edwards EnterpriseOne adapter</span></span>](../core/jd-edwards-enterpriseone-adapter.md) 
  
-   [<span data-ttu-id="a4870-118">Adaptador de JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="a4870-118">JD Edwards OneWorld adapter</span></span>](../core/jd-edwards-oneworld-adapter.md)  
  
-   [<span data-ttu-id="a4870-119">Adaptador de Oracle E-Business Suite ODBC</span><span class="sxs-lookup"><span data-stu-id="a4870-119">Oracle E-Business Suite ODBC adapter</span></span>](../core/oracle-e-business-suite-odbc-adapter.md)  
  
-   [<span data-ttu-id="a4870-120">Adaptador de bases de datos ODBC de Oracle</span><span class="sxs-lookup"><span data-stu-id="a4870-120">Oracle Database ODBC adapter</span></span>](../core/oracle-database-odbc-adapter.md)  
  
-   [<span data-ttu-id="a4870-121">Adaptador de PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4870-121">PeopleSoft Enterprise adapter</span></span>](../core/peoplesoft-enterprise-adapter.md)  
  
-   [<span data-ttu-id="a4870-122">Adaptador de aplicaciones Siebel eBusiness</span><span class="sxs-lookup"><span data-stu-id="a4870-122">Siebel eBusiness Applications adapter</span></span>](../core/siebel-ebusiness-applications-adapter.md)  
  
-   [<span data-ttu-id="a4870-123">Adaptador TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="a4870-123">TIBCO Enterprise Message Service adapter</span></span>](../core/tibco-enterprise-message-service-adapter.md)  
  
-   [<span data-ttu-id="a4870-124">Adaptador de TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="a4870-124">TIBCO Rendezvous adapter</span></span>](../core/tibco-rendezvous-adapter.md)  
  
-   [<span data-ttu-id="a4870-125">Adaptador de MQSeries</span><span class="sxs-lookup"><span data-stu-id="a4870-125">MQSeries adapter</span></span>](../core/mqseries-adapter.md)  
  
-   [<span data-ttu-id="a4870-126">Adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="a4870-126">MSMQ adapter</span></span>](../core/msmq-adapter.md)  
  
-   [<span data-ttu-id="a4870-127">Adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="a4870-127">POP3 adapter</span></span>](../core/pop3-adapter.md)  
  
-   [<span data-ttu-id="a4870-128">Adaptador SAP</span><span class="sxs-lookup"><span data-stu-id="a4870-128">SAP adapter</span></span>](../core/sap-adapter.md)  
  
-   [<span data-ttu-id="a4870-129">Adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="a4870-129">SMTP adapter</span></span>](../core/smtp-adapter.md)  
  
-   [<span data-ttu-id="a4870-130">Adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="a4870-130">SOAP adapter</span></span>](../core/soap-adapter.md)  
  
-   [<span data-ttu-id="a4870-131">Adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="a4870-131">SQL adapter</span></span>](../core/sql-adapter.md)  
  
-   [<span data-ttu-id="a4870-132">Adaptador de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="a4870-132">Windows SharePoint Services adapter</span></span>](../core/windows-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="a4870-133">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="a4870-133">WCF adapters</span></span>](../core/wcf-adapters.md)  
  
-   [<span data-ttu-id="a4870-134">Crear y eliminar controladores de adaptador</span><span class="sxs-lookup"><span data-stu-id="a4870-134">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)  
  
-   [<span data-ttu-id="a4870-135">Parámetros de configuración que afectan al rendimiento del adaptador</span><span class="sxs-lookup"><span data-stu-id="a4870-135">Configuration Parameters that Affect Adapter Performance</span></span>](../core/configuration-parameters-that-affect-adapter-performance.md)  
  
-   [<span data-ttu-id="a4870-136">Solución de problemas de adaptadores de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a4870-136">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="a4870-137">Información adicional del adaptador</span><span class="sxs-lookup"><span data-stu-id="a4870-137">Additional Adapter Information</span></span>](../core/additional-adapter-information.md)
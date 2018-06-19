---
title: Introducción a la seguridad de la implementación | Documentos de Microsoft
description: Vínculos rápidos sobre seguridad, cifrado, los grupos de usuarios en la implementación de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c5a000-9f6b-49db-bd87-8c694240a192
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5ff5db17739e2db407bdb52bd3f9aad4e61b74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299548"
---
# <a name="securing-your-biztalk-server-deployment"></a><span data-ttu-id="9900c-103">Proteger la implementación de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9900c-103">Securing Your BizTalk Server Deployment</span></span>
<span data-ttu-id="9900c-104">En los temas de esta sección se proporcionan los vínculos que tratan sobre la configuración de puertos de firewall, el protocolo de seguridad de Internet (IPSec) y la seguridad de Capa de sockets seguros (SSL) una vez que se ha instalado y configurado BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9900c-104">The topics in this section provide the links about configuring firewall ports, Internet protocol security (IPSec), and secure sockets layer (SSL) security after you have installed and configured BizTalk.</span></span>  
  
-   <span data-ttu-id="9900c-105">Para obtener más información sobre cómo implementar SSL en un servidor web, consulte [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059).</span><span class="sxs-lookup"><span data-stu-id="9900c-105">For more information about how to implement SSL in a Web server, see [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059).</span></span>  
  
-   <span data-ttu-id="9900c-106">Para obtener más información sobre cómo habilitar el cifrado entre SQL Server y sus clientes, tales como servidores de procesamiento y clientes de administración, consulte [Cifrado de datos transparente (TDE)](https://msdn.microsoft.com/library/bb934049.aspx).</span><span class="sxs-lookup"><span data-stu-id="9900c-106">For more information about how to enable encryption between SQL Server and its clients such as processing servers and administration clients, see [Transparent Data Encryption (TDE)](https://msdn.microsoft.com/library/bb934049.aspx).</span></span>  
  
-   <span data-ttu-id="9900c-107">Para obtener más información sobre cómo configurar la administración de identidades para los servidores locales, consulte [Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/).</span><span class="sxs-lookup"><span data-stu-id="9900c-107">For more information about how to configure identity management for your on-premises servers, see [Identity Manager ](https://docs.microsoft.com/microsoft-identity-manager/).</span></span>  
  
 <span data-ttu-id="9900c-108">Además de los temas de esta sección, debería revisar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="9900c-108">In addition to the topics in this section, you should review the following information:</span></span>  
  
-   <span data-ttu-id="9900c-109">Para obtener información conceptual sobre el planeamiento y el mantenimiento de una implementación segura, consulte [Planear la seguridad](../core/planning-for-security.md).</span><span class="sxs-lookup"><span data-stu-id="9900c-109">For conceptual information about planning and maintaining a secure deployment, see [Planning for Security](../core/planning-for-security.md).</span></span>  
  
-   <span data-ttu-id="9900c-110">Para obtener información sobre la configuración del acceso para administradores y usuarios del sistema, consulte [Administración de seguridad de BizTalk Server](../core/managing-biztalk-server-security.md).</span><span class="sxs-lookup"><span data-stu-id="9900c-110">For information about configuring access for administrators and system users, see [Managing BizTalk Server Security](../core/managing-biztalk-server-security.md).</span></span>  
  
-   <span data-ttu-id="9900c-111">Para obtener más información sobre las características de seguridad de BizTalk Server, consulte [Proteger los mensajes de BizTalk](../core/secure-and-protect-your-biztalk-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9900c-111">For more information about security features in BizTalk Server, see [Secure and protect your BizTalk messages](../core/secure-and-protect-your-biztalk-messages.md).</span></span>  
  
-   <span data-ttu-id="9900c-112">Para obtener más información sobre cómo implementar mensajes seguros, consulte [Implementar seguridad en los mensajes](../core/implementing-message-security.md).</span><span class="sxs-lookup"><span data-stu-id="9900c-112">For more information about how to implement secure messages, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
-   <span data-ttu-id="9900c-113">Para obtener más información sobre de las cuentas de grupos y de usuario de Windows que usa BizTalk Server, consulte [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="9900c-113">For more information about Windows groups and user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="9900c-114">Temas adicionales sobre configuración</span><span class="sxs-lookup"><span data-stu-id="9900c-114">Additional Configuration Topics</span></span>  
 
 [<span data-ttu-id="9900c-115">Configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9900c-115">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="9900c-116">Configurar BizTalk Server en una máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="9900c-116">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[<span data-ttu-id="9900c-117">Configuración de BizTalk Server en un clúster</span><span class="sxs-lookup"><span data-stu-id="9900c-117">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
    
  
## <a name="see-also"></a><span data-ttu-id="9900c-118">Ver también</span><span class="sxs-lookup"><span data-stu-id="9900c-118">See Also</span></span>  
 <span data-ttu-id="9900c-119">[Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md) </span><span class="sxs-lookup"><span data-stu-id="9900c-119">[Access Control and Data Security](../core/access-control-and-data-security.md) </span></span>  
 <span data-ttu-id="9900c-120">[Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="9900c-120">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="9900c-121">[Planear la seguridad](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="9900c-121">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="9900c-122">Diseñar las arquitecturas del sistema de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="9900c-122">Designing the System Architectures for BizTalk Server</span></span>](../core/designing-the-system-architectures-for-biztalk-server.md)   

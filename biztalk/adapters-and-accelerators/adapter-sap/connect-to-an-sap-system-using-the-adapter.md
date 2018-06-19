---
title: Conectarse a un sistema SAP mediante el adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- adapters, connecting to an SAP system
- connection string
ms.assetid: d506a948-5f4a-420b-a404-508824683099
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75f8c4b8650b2c81b3b82bf520958646e20da380
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216900"
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a><span data-ttu-id="82c19-102">Conectarse a un sistema SAP mediante el adaptador</span><span class="sxs-lookup"><span data-stu-id="82c19-102">Connect to an SAP system using the adapter</span></span>
<span data-ttu-id="82c19-103">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requiere que los clientes de adaptador proporcionar una cadena de conexión que se denomina conexión de identificador uniforme de recursos (URI) para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="82c19-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI) to connect to the SAP system.</span></span> <span data-ttu-id="82c19-104">Con un URI de conexión, los clientes de adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo. Para obtener más información sobre el URI de conexión, consulte [crear una conexión con el sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span><span class="sxs-lookup"><span data-stu-id="82c19-104">With a connection URI, adapter clients can specify connection parameters to connect to an external system.For more information about the connection URI, see [Create a connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
 <span data-ttu-id="82c19-105">Asegúrese de que cumple con las normas de seguridad al establecer una conexión con un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="82c19-105">Make sure you comply with the security guidelines when establishing a connection with an SAP system.</span></span> <span data-ttu-id="82c19-106">Para obtener más información acerca de las instrucciones de seguridad, consulte [proteger sus aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).</span><span class="sxs-lookup"><span data-stu-id="82c19-106">For more information about security guidelines, see [Secure your SAP applications](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).</span></span>
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a><span data-ttu-id="82c19-107">¿El número de conexiones puede el adaptador abierto al sistema SAP?</span><span class="sxs-lookup"><span data-stu-id="82c19-107">How Many Connections Can the Adapter Open to the SAP System?</span></span>  
 <span data-ttu-id="82c19-108">De forma predeterminada, el sistema SAP permite a los clientes abrir 100 conexiones al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="82c19-108">By default, the SAP system enables clients to open 100 connections to the SAP system.</span></span> <span data-ttu-id="82c19-109">Sin embargo, puede establecer una variable de entorno en el equipo que ejecuta el sistema SAP para aumentar el límite del número de conexiones.</span><span class="sxs-lookup"><span data-stu-id="82c19-109">However, you can set an environment variable on the computer running the SAP system to increase the limit on the number of connections.</span></span> <span data-ttu-id="82c19-110">Para obtener más información, consulte [solucionar problemas de funcionamiento con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="82c19-110">For more information, see [Troubleshoot Operational Issues with the SAP adapter](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c19-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="82c19-111">See Also</span></span>  
 [<span data-ttu-id="82c19-112">Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="82c19-112">Architecture overview of the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)
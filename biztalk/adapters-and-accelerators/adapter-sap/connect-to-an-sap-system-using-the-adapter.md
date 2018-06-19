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
# <a name="connect-to-an-sap-system-using-the-adapter"></a>Conectarse a un sistema SAP mediante el adaptador
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requiere que los clientes de adaptador proporcionar una cadena de conexión que se denomina conexión de identificador uniforme de recursos (URI) para conectarse al sistema SAP. Con un URI de conexión, los clientes de adaptador pueden especificar parámetros de conexión para conectarse a un sistema externo. Para obtener más información sobre el URI de conexión, consulte [crear una conexión con el sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).  
  
 Asegúrese de que cumple con las normas de seguridad al establecer una conexión con un sistema SAP. Para obtener más información acerca de las instrucciones de seguridad, consulte [proteger sus aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a>¿El número de conexiones puede el adaptador abierto al sistema SAP?  
 De forma predeterminada, el sistema SAP permite a los clientes abrir 100 conexiones al sistema SAP. Sin embargo, puede establecer una variable de entorno en el equipo que ejecuta el sistema SAP para aumentar el límite del número de conexiones. Para obtener más información, consulte [solucionar problemas de funcionamiento con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)
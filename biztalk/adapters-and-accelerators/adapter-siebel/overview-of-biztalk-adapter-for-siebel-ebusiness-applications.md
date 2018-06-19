---
title: Información general del adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcc3a90f7025a5f396cd778676f5f3152bc7657
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222044"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>Información general del adaptador de BizTalk para Siebel eBusiness Applications
La [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone el sistema Siebel como un servicio WCF. Los clientes de adaptador pueden realizar operaciones en el sistema Siebel mediante el intercambio de mensajes SOAP con el adaptador. El adaptador utiliza el mensaje de WCF y realiza las llamadas adecuadas al sistema Siebel para realizar la operación. El adaptador devuelve la respuesta en el sistema Siebel al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] metadatos de las superficies de artefactos de Siebel (componentes empresariales, servicios de negocio) que describen la estructura de SOAP del mensaje en forma de WSDL. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] utiliza la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones y genera los artefactos de programación que se pueden usar en la solución de programación.  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] usa el Control de datos de Siebel COM para tener acceso al sistema Siebel. El Control de datos de Siebel COM viene incluido con el cliente Siebel Web. Por lo tanto, asegúrese de que tiene instalado en el mismo equipo que el cliente de Siebel Web el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Puede usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para comunicarse con el sistema Siebel de las maneras siguientes:  
  
-   Al desarrollar aplicaciones de BizTalk. Vea [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).
  
-   Mediante el modelo de servicio WCF. Vea [desarrollar aplicaciones Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).  
  
-   Mediante el modelo de canal WCF. Consulte desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF[escriba la descripción del vínculo](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador a un sistema Siebel?](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)  
  
-   [¿Cómo los metadatos de Siebel expuesta del adaptador?](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)  
  
-   [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [Otras características admitidas por el adaptador](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx) 
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
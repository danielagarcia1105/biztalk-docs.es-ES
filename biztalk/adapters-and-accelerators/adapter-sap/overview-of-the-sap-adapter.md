---
title: Información general sobre el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3031bdf1317d96f64f1ea247c6f8cbf83e1688c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-sap-adapter"></a>Información general sobre el adaptador SAP
La [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone el sistema SAP como un servicio WCF. Los clientes de adaptador pueden realizar operaciones en el sistema SAP mediante el intercambio de mensajes SOAP con el adaptador. El adaptador utiliza el mensaje de WCF y realiza las llamadas adecuadas al sistema SAP para realizar la operación. El adaptador devuelve la respuesta desde el sistema SAP al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] metadatos de las superficies de artefactos SAP (RFC, BAPI, IDOC) que describen la estructura de SOAP del mensaje en forma de WSDL. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utiliza [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones y genera los artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la biblioteca de Unicode RFC, librfc32u.dll, para comunicarse con el sistema SAP, además de usar otros archivos DLL auxiliar. Para obtener una lista completa de los archivos DLL de SAP que requiere el adaptador, vea la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Guía de instalación. La Guía de instalación se instala normalmente en \<unidad de instalación:\>archivos \Program\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents. Puede usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para comunicarse con el sistema SAP de las maneras siguientes:  
  
-   Al desarrollar aplicaciones de BizTalk. Vea [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md) para obtener más información.  
  
-   Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Vea [aplicaciones SAP desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).
  
-   Mediante el modelo de canal WCF. Vea [aplicaciones SAP desarrollar mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador a un sistema SAP?](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [¿Cómo los metadatos de adaptador SAP expuesta?](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [Otras características admitidas por el adaptador](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)
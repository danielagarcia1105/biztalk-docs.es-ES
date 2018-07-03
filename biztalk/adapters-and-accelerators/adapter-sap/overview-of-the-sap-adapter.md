---
title: Información general sobre el adaptador de SAP | Microsoft Docs
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
ms.openlocfilehash: 58f6249774697e12e12ab5b85bccf6df210a5d4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981845"
---
# <a name="overview-of-the-sap-adapter"></a>Información general sobre el adaptador de SAP
La [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone el sistema SAP como un servicio WCF. Los clientes del adaptador pueden realizar operaciones en el sistema SAP mediante el intercambio de mensajes SOAP con el adaptador. El adaptador utiliza el mensaje de WCF y realiza las llamadas adecuadas al sistema SAP para realizar la operación. El adaptador devuelve la respuesta desde el sistema SAP al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] metadatos de las superficies de artefactos SAP (RFC, BAPI, IDOC) que describen la estructura de SOAP del mensaje en el formulario de WSDL. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes del adaptador recuperar metadatos para operaciones y genera los artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectar con el sistema SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la biblioteca de Unicode RFC, librfc32u.dll, para comunicarse con el sistema SAP, además de usar otro DLL compatibles. Para obtener una lista completa de archivos DLL de SAP que requiere el adaptador, vea la [Guía de instalación de BizTalk Adapter Pack](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap). Puede usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para comunicarse con el sistema SAP de las maneras siguientes:  
  
- Mediante el desarrollo de aplicaciones de BizTalk. Consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md) para obtener más información.  
  
- Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Consulte [aplicaciones de desarrollo de SAP mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).
  
- Mediante el modelo de canal WCF. Consulte [aplicaciones de desarrollo de SAP mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador a un sistema SAP?](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [¿Cómo los metadatos de adaptador SAP expuesta?](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [Otras características admitidas por el adaptador](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)
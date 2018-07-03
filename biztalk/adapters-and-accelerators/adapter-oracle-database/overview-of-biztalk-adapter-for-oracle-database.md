---
title: Información general del adaptador de BizTalk para Oracle Database | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, overview
- ODP.NET
- Oracle Data Provider for .NET 2.0
ms.assetid: 852b8f82-ab34-45b8-ad7f-263d719a87f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d6629672ac1bbfdd5e0bc4e01cee37c5d71d137
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005181"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a>Información general del adaptador de BizTalk para Oracle Database
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone la base de datos de Oracle como un servicio WCF. Los clientes del adaptador pueden realizar operaciones en la base de datos de Oracle mediante el intercambio de mensajes SOAP con el adaptador. El adaptador utiliza el mensaje de WCF y realiza llamadas ODP.NET adecuadas para realizar la operación. El adaptador devuelve la respuesta de la base de datos de Oracle al cliente en forma de mensajes SOAP.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] metadatos de las superficies de artefactos de base de datos de Oracle (tablas, funciones, procedimientos, etc.) que describen la estructura de SOAP del mensaje en el formulario de WSDL. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para permitir que los clientes del adaptador recuperar metadatos para operaciones y genera los artefactos de programación que se pueden usar en la solución de programación.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa el proveedor de datos de Oracle para .NET (ODP.NET) para comunicarse con la base de datos de Oracle. Puede usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para comunicarse con la base de datos de Oracle de las maneras siguientes:  
  
- Mediante el desarrollo de aplicaciones de BizTalk. Consulte [desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md) para obtener más información.  
  
- Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Consulte [aplicaciones de desarrollo de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) para obtener más información.  
  
- Mediante el modelo de canal WCF. Consulte [aplicaciones de desarrollo de base de datos de Oracle mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) para obtener más información.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [¿Cómo se conecta el adaptador en una base de datos de Oracle?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)  
  
-   [¿Cómo los metadatos de adaptador Oracle expuesta?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)  
  
-   [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)  
  
-   [¿Cómo el adaptador controlar transacciones?](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [Compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [Las operaciones que son compatibles con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a>Vea también  
 [Descripción del adaptador de Biztalk para Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)
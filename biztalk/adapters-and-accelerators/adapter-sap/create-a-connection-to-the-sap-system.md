---
title: "Crear una conexión con el sistema SAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9835047fd32556e6bd9f42adb768ce62f4536ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-sap-system"></a>Crear una conexión con el sistema SAP.
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, habilita la comunicación con un sistema SAP a través de una dirección de extremo WCF. En WCF, la dirección del extremo identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se utiliza para establecer una conexión con el sistema SAP. Debe especificar un URI de conexión al que:  
  
-   Cuando se crea un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal o cuando se crea un host de servicio o cliente WCF con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
-   Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
 Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] y el sistema SAP proporcionando con:  
  
-   Información sobre las propiedades de conexión y la estructura del URI de conexión de SAP.  
  
-   Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear el URI de conexión de sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)
---
title: Crear una conexión al sistema SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef25dddf3d30f584b30aa0f35b8b1c4140d285e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965813"
---
# <a name="create-a-connection-to-the-sap-system"></a>Crear una conexión con el sistema SAP.
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, permite la comunicación a un sistema SAP a través de una dirección de extremo WCF. En WCF, la dirección de punto de conexión identifica la ubicación de red de un servicio y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa para establecer una conexión con el sistema SAP. Debe especificar un URI de conexión cuando le:  
  
- Cuando se crea un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal o al crear un host de servicio o cliente WCF mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
- Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
  Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] y el sistema SAP, ya que con:  
  
- Información sobre las propiedades de conexión y la estructura de lo URI de conexión de SAP.  
  
- Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Crear el URI de conexión del sistema SAP](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)
---
title: "Crear una conexión con el sistema Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a108335263e85db832f4db144d27b64b92429683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-siebel-system"></a>Crear una conexión con el sistema Siebel
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, habilita la comunicación con un sistema Siebel a través de una dirección de extremo WCF. En WCF, la dirección del extremo identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se utiliza para establecer una conexión con el sistema Siebel. Debe especificar un URI de conexión al que:  
  
-   Crear un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canal modelo o crear un host de servicio o cliente WCF con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
-   Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF, o interfaz de servicio WCF para una [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
-   Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
-   Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
 Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] y el sistema Siebel proporcionando con:  
  
-   Información sobre las propiedades de conexión y la estructura del URI de conexión de Siebel.  
  
-   Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)
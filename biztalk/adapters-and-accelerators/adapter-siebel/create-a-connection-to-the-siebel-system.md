---
title: Crear una conexión al sistema Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7710d25528cadff3d082fc067f951830f2bb8efe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013117"
---
# <a name="create-a-connection-to-the-siebel-system"></a>Crear una conexión con el sistema de Siebel
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Por lo tanto, permite la comunicación a un sistema de Siebel a través de una dirección de extremo WCF. En WCF, la dirección de punto de conexión identifica la ubicación de red de un servicio y normalmente se expresa como un identificador uniforme de recursos (URI). El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] usa para establecer una conexión con el sistema Siebel. Debe especificar un URI de conexión cuando le:  
  
- Crear un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de canal o crear un host de servicio o cliente WCF mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.  
  
- Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF, o interfaz de servicio WCF para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.  
  
- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
- Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF, o interfaz de servicio WCF para una solución de modelo de servicio WCF.  
  
  Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] y el sistema de Siebel, ya que con:  
  
- Información sobre las propiedades de conexión y la estructura de lo URI de conexión de Siebel.  
  
- Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)
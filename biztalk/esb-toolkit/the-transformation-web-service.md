---
title: "El servicio Web de transformación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-transformation-web-service"></a>El servicio Web de transformación
El servicio Web de transformación permite que aplicaciones externas para enviar un documento a una aplicación de ESB y hacer que se transforma utilizando una asignación de Microsoft BizTalk implementada. Al contrario que el agente de transformación, este servicio no enruta mensajes a través de la base de datos de cuadro de mensaje de BizTalk.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF). Los nombres de servicio son **ESB. TransformServices** y **ESB. TransformServices.WCF**, respectivamente, y los servicios exponen un método único:  
  
-   **Transformar.** Este método toma como parámetros un **cadena** que contiene el mensaje que se va a transformar y un **cadena** que contiene el nombre completo de un mapa que se implementan en BizTalk. El método devuelve un **cadena** que contiene el documento transformado. El uso de parámetros de cadena reduce el riesgo de problemas de interoperabilidad en un entorno heterogéneo; Sin embargo, tenga en cuenta que esto es un servicio Web, por lo que debería evitar utilizarla para transformar documentos de gran tamaño (el servicio de transformación de BizTalk es más adecuado para documentos de gran tamaño).  
  
> [!NOTE]
>  De forma predeterminada, los servicios Web de transformación no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes. Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor de BizTalk mediante IPSec de nivel de red y acceso de nivel de archivo adecuado permisos de control de lista (ACL).
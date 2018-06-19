---
title: Ejemplos de adaptadores HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1111322d59f8ff5c6ba6209aa48eb515a23c72f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970986"
---
# <a name="http-adapter-samples"></a>Ejemplos de adaptadores de HTTP
Esta sección contiene ejemplos que muestran la funcionalidad avanzada para configurar el adaptador de HTTP de BizTalk.  
  
> [!NOTE]
>  Antes de ejecutar este ejemplo, lleve a cabo los siguientes pasos:  
>   
>  1.  Abra IIS y agregue restricciones de ISAPI y CGI:  
>   
>      Haga clic en el nombre del equipo en el panel izquierdo, haga clic en "Restricciones de ISAPI y CGI" en el panel derecho y, a continuación, agregue la ruta de acceso de ISAPI o CGI:  
>   
>      En un equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\BTSHTTPReceive.dll  
>   
>      En un equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\BTSHTTPReceive.dll  
>   
>      Marque la casilla Permitir ejecución de la ruta de extensión.  
> 2.  Haga clic en "HTTPRequestResponseSample" en panel izquierdo, haga clic en "Asignaciones de controlador" en el panel central y, a continuación, haga clic en "Agregar asignación de script" con el siguiente valor:  
>   
>      Ruta de acceso de solicitudes:BTSHTTPReceive.dll  
>   
>      Ejecutable:  
>   
>      En el equipo de 64 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive64\  
>   
>      En el equipo de 32 bits agregue: C:\Program Files (x86) \Microsoft BizTalk Server \<versión\>\HttpReceive\  
>   
>      Restricciones de solicitudes:  
>   
>      Verbos: POST  
>   
>      Acceso: Script  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [HTTPSolicitResponse](../core/httpsolicitresponse.md)  
  
-   [HTTPRequestResponse](../core/httprequestresponse.md)
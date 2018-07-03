---
title: Cómo diagnosticar problemas con Windows SharePoint Services adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c29569-3814-43a7-93f8-a39c3464a831
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd328b8e68b90b5afb23a49fc7412156fc85de91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981013"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a>Diagnóstico de problemas con el adaptador de Windows SharePoint Services
Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de Windows Sharepoint Services.  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>Comprobar si existen errores detallados en los archivos de registro de IIS y HTTPERR del servidor IIS  
  
- Los archivos de registro del servidor IIS de origen o destino pueden contener información útil para la solución de problemas con el adaptador de Windows Sharepoint Services. De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.  
  
- De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  El archivo de registro de HTTPERR solo está disponible en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solución de problemas del adaptador de Windows SharePoint Services](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)
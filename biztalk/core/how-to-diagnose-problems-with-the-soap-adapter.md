---
title: Cómo diagnosticar problemas con el adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85c585c3fae6c6f49412f00e02276276e9c73b64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968317"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>Cómo diagnosticar problemas con el adaptador de SOAP
Esta sección contiene los pasos que se pueden seguir para diagnosticar problemas con el adaptador de SOAP.  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>Compruebe si existen errores detallados en el registro de IIS y HTTPERR del servidor IIS  
  
- El origen o el destino de los archivos de registro del servidor IIS pueden contener información útil para la solución de problemas con el adaptador de SOAP. De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.  
  
   De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  El archivo de registro de HTTPERR está disponible solo en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solucionar problemas del adaptador SOAP](../core/troubleshooting-the-soap-adapter.md)
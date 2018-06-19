---
title: Cómo diagnosticar problemas con el adaptador de SOAP | Documentos de Microsoft
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
ms.openlocfilehash: db1d495eb301f93100a6ac9a4e50c8f1c57e5f5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249476"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>Cómo diagnosticar problemas con el adaptador de SOAP
Esta sección contiene los pasos que se pueden seguir para diagnosticar problemas con el adaptador de SOAP.  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>Compruebe si existen errores detallados en el registro de IIS y HTTPERR del servidor IIS  
  
-   El origen o el destino de los archivos de registro del servidor IIS pueden contener información útil para la solución de problemas con el adaptador de SOAP. De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:  
  
     *% WinDir %\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor IIS.  
  
     De forma predeterminada, en un equipo basado en [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] los archivos de registro de HTTPERR se ubican en el siguiente directorio:  
  
     *% WinDir %\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  El archivo de registro de HTTPERR está disponible solo en equipos con [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solucionar problemas del adaptador SOAP](../core/troubleshooting-the-soap-adapter.md)
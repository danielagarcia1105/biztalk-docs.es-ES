---
title: Cómo diagnosticar problemas con el adaptador de FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28d920a7bdc61e98832fb6818f66182ab69acbf2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987221"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>Cómo diagnosticar problemas con el adaptador de FTP
Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de FTP.  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>Comprobar la existencia de errores detallados en los archivos de registro de FTP del servidor FTP  
  
- El origen o el destino de los archivos de registro del servidor FTP puede contener información útil para la solución de problemas con el adaptador de FTP. De forma predeterminada, en un equipo con Windows Server o Windows XP, los archivos de registro de FTP se encuentran en el siguiente directorio:  
  
   <em>% WinDir %\\</em>system32\LogFiles\MSFTPSVC1\  
  
  > [!NOTE]
  >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor FTP.  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>Habilitar el registro para el puerto de envío o la ubicación de recepción FTP  
  
-   Configurar el FTP ubicación de recepción o puerto de envío con un **registro** carpeta. El adaptador de FTP guardará la información de registro detallada en esta carpeta. El **registro** carpeta opción está disponible en el **propiedades de transporte FTP** cuadro de diálogo al configurar un puerto de envío o ubicación de recepción con el tipo de transporte FTP.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)
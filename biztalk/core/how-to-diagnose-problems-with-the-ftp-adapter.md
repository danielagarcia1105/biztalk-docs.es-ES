---
title: Cómo diagnosticar problemas con el adaptador de FTP | Documentos de Microsoft
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
ms.openlocfilehash: 4e66be2e498449b1cdcc70e05c6195ccd8e4395d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248772"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a>Cómo diagnosticar problemas con el adaptador de FTP
Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de FTP.  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a>Comprobar la existencia de errores detallados en los archivos de registro de FTP del servidor FTP  
  
-   El origen o el destino de los archivos de registro del servidor FTP puede contener información útil para la solución de problemas con el adaptador de FTP. De forma predeterminada, en un equipo con Windows Server o Windows XP, los archivos de registro de FTP se encuentran en el siguiente directorio:  
  
     *% WinDir %\\*system32\LogFiles\MSFTPSVC1\  
  
    > [!NOTE]
    >  *% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor FTP.  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a>Habilitar el registro para el puerto de envío o la ubicación de recepción FTP  
  
-   Configurar FTP ubicación de recepción o puerto de envío con un **registro** carpeta. El adaptador de FTP guardará la información de registro detallada en esta carpeta. El **registro** carpeta opción está disponible en la **propiedades de transporte FTP** cuadro de diálogo cuando se configura un puerto de envío o ubicación de recepción con el tipo de transporte FTP.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)
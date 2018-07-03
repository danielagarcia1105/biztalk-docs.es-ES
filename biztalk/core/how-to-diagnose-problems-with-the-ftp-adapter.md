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
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a><span data-ttu-id="0046b-102">Cómo diagnosticar problemas con el adaptador de FTP</span><span class="sxs-lookup"><span data-stu-id="0046b-102">How to Diagnose Problems with the FTP Adapter</span></span>
<span data-ttu-id="0046b-103">Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="0046b-103">This section contains steps that can be followed to help diagnose problems with the FTP adapter.</span></span>  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a><span data-ttu-id="0046b-104">Comprobar la existencia de errores detallados en los archivos de registro de FTP del servidor FTP</span><span class="sxs-lookup"><span data-stu-id="0046b-104">Check the FTP log files on the FTP Server for errors</span></span>  
  
- <span data-ttu-id="0046b-105">El origen o el destino de los archivos de registro del servidor FTP puede contener información útil para la solución de problemas con el adaptador de FTP.</span><span class="sxs-lookup"><span data-stu-id="0046b-105">The source or target FTP server log files can contain information that is helpful for troubleshooting problems with the FTP adapter.</span></span> <span data-ttu-id="0046b-106">De forma predeterminada, en un equipo con Windows Server o Windows XP, los archivos de registro de FTP se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="0046b-106">By default the FTP log files on a Windows Server or Windows XP computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="0046b-107"><em>% WinDir %\\</em>system32\LogFiles\MSFTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="0046b-107"><em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0046b-108">*% WinDir %* es un marcador de posición para la ubicación del directorio de Windows en el servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="0046b-108">*%WinDir%* is a placeholder for the location of the Windows directory on the FTP server.</span></span>  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a><span data-ttu-id="0046b-109">Habilitar el registro para el puerto de envío o la ubicación de recepción FTP</span><span class="sxs-lookup"><span data-stu-id="0046b-109">Enable logging for the FTP Receive location or Send Port</span></span>  
  
-   <span data-ttu-id="0046b-110">Configurar el FTP ubicación de recepción o puerto de envío con un **registro** carpeta.</span><span class="sxs-lookup"><span data-stu-id="0046b-110">Configure the FTP receive location or send port with a **Log** folder.</span></span> <span data-ttu-id="0046b-111">El adaptador de FTP guardará la información de registro detallada en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="0046b-111">The FTP adapter will save detailed logging information to this folder.</span></span> <span data-ttu-id="0046b-112">El **registro** carpeta opción está disponible en el **propiedades de transporte FTP** cuadro de diálogo al configurar un puerto de envío o ubicación de recepción con el tipo de transporte FTP.</span><span class="sxs-lookup"><span data-stu-id="0046b-112">The **Log** folder option is available on the **FTP Transport Properties** dialog box when configuring a receive location or send port with the FTP transport type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0046b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0046b-113">See Also</span></span>  
 [<span data-ttu-id="0046b-114">Herramientas y utilidades que se utilizan para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="0046b-114">Tools and Utilities to Use for Troubleshooting</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)